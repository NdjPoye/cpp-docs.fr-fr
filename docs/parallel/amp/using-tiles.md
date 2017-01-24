---
title: "Utilisation des mosa&#239;ques | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
caps.latest.revision: 18
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des mosa&#239;ques
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la disposition en mosaïque pour optimiser l'accélération de votre application.  Les mosaïques divisent les threads en sous\-ensembles rectangulaires égaux ou *mosaïques*.  Si vous utilisez une taille appropriée de mosaïque et un algorithme en mosaïque, vous pouvez obtenir bien plus d'accélération de votre code C\+\+ AMP.  Les composants de base de la mosaïque sont :  
  
-   Variables `tile_static`.  L'avantage principal des mosaïques est le gain de performances des accès `tile_static`.  L'accès aux données en mémoire dans `tile_static` peut être beaucoup plus rapide que l'accès aux données dans l'espace global \(`array` ou objets `array_view`\).  Une instance d'une variable `tile_static` est créée pour chaque mosaïque et tous les threads de la mosaïque ont accès à la variable.  Dans un algorithme en mosaïque classique, les données sont copiées dans la mémoire `tile_static` à partir de la mémoire globale, puis accédées ensuite plusieurs fois à partir de la mémoire `tile_static`.  
  
-   [tile\_barrier::wait, méthode](../Topic/tile_barrier::wait%20Method.md).  Un appel à `tile_barrier::wait` interrompt l'exécution du thread actuel jusqu'à ce que tous les threads de la même mosaïque atteignent l'appel à `tile_barrier::wait`.  Vous ne pouvez pas garantir l'ordre dans lequel les threads s'exécuteront, uniquement qu'aucun thread dans la mosaïque ne s'exécutera après l'appel à `tile_barrier::wait` jusqu'à ce que tous les threads aient atteint l'appel.  Cela signifie qu'à l'aide de la méthode `tile_barrier::wait`, vous pouvez effectuer des tâches mosaïque par mosaïque plutôt que thread par thread.  Un algorithme classique de pavage a le code pour initialiser la mémoire `tile_static` de l'ensemble de la mosaïque, suivi d'un appel à `tile_barrer::wait`.  Le code qui suit `tile_barrier::wait` contient les calculs qui requièrent l'accès à toutes les valeurs `tile_static`.  
  
-   Indexation locale et globale.  Vous avez accès à l'index du thread par rapport à la totalité de l'objet `array_view` ou à l'objet `array` et à l'index relatif à la mosaïque.  Utiliser l'index local peut simplifier la lecture et le débogage de votre code.  En général, vous utilisez l'indexation locale pour accéder à des variables `tile_static`, et l'indexation globale pour accéder aux variables `array` et  `array_view`.  
  
-   [tiled\_extent, classe](../../parallel/amp/reference/tiled-extent-class.md) et [tiled\_index, classe](../../parallel/amp/reference/tiled-index-class.md).  Vous utilisez un objet `tiled_extent` au lieu d'un objet `extent` dans l'appel de `parallel_for_each`.  Vous utilisez un objet `tiled_index` au lieu d'un objet `index` dans l'appel de `parallel_for_each`.  
  
 Pour tirer parti des mosaïques, votre algorithme doit partitionner le domaine de calcul dans des mosaïques, puis copier les données de mosaïque dans des variables `tile_static` pour obtenir un accès plus rapide.  
  
## Exemple d'indices globaux, de mosaïques et locaux  
 Le diagramme suivant représente une matrice 8x9 des données qui sont organisées en mosaïques 2x3.  
  
 ![Matrice 8 x 9 divisée en mosaïques 2 x 3](../../parallel/amp/media/usingtilesmatrix.png "UsingTilesMatrix")  
  
 L'exemple suivant affiche les index globaux, de mosaïques et locaux de cette matrice en mosaïque.  Un objet `array_view` est créé à l'aide des éléments de type `Description`.  La `Description` contient les indices globaux, de la mosaïque et locaux de l'élément de la matrice.  Le code dans l'appel à `parallel_for_each` définit les valeurs des indices globaux, de la mosaïque et locaux de chaque élément.  La sortie affiche les valeurs dans les structures `Description`.  
  
```cpp  
  
#include <iostream>  
#include <iomanip>  
#include <Windows.h>  
#include <amp.h>  
using namespace concurrency;  
  
const int ROWS = 8;  
const int COLS = 9;  
  
// tileRow and tileColumn specify the tile that each thread is in.  
// globalRow and globalColumn specify the location of the thread in the array_view.  
// localRow and localColumn specify the location of the thread relative to the tile.  
struct Description {  
    int value;  
    int tileRow;  
    int tileColumn;  
    int globalRow;  
    int globalColumn;  
    int localRow;  
    int localColumn;  
};  
  
// A helper function for formatting the output.  
void SetConsoleColor(int color) {  
    int colorValue = (color == 0) ? 4 : 2;  
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), colorValue);  
}  
  
// A helper function for formatting the output.  
void SetConsoleSize(int height, int width) {  
    COORD coord; coord.X = width; coord.Y = height;  
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);  
    SMALL_RECT* rect = new SMALL_RECT();  
    rect->Left = 0; rect->Top = 0; rect->Right = width; rect->Bottom = height;  
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);  
}  
  
// This method creates an 8x9 matrix of Description structures. In the call to parallel_for_each, the structure is updated   
// with tile, global, and local indices.  
void TilingDescription() {  
    // Create 72 (8x9) Description structures.  
    std::vector<Description> descs;  
    for (int i = 0; i < ROWS * COLS; i++) {  
        Description d = {i, 0, 0, 0, 0, 0, 0};  
        descs.push_back(d);  
    }  
  
    // Create an array_view from the Description structures.  
    extent<2> matrix(ROWS, COLS);  
    array_view<Description, 2> descriptions(matrix, descs);  
  
    // Update each Description with the tile, global, and local indices.  
    parallel_for_each(descriptions.extent.tile< 2, 3>(),  
         [=] (tiled_index< 2, 3> t_idx) restrict(amp)   
    {  
        descriptions[t_idx].globalRow = t_idx.global[0];  
        descriptions[t_idx].globalColumn = t_idx.global[1];  
        descriptions[t_idx].tileRow = t_idx.tile[0];  
        descriptions[t_idx].tileColumn = t_idx.tile[1];  
        descriptions[t_idx].localRow = t_idx.local[0];  
        descriptions[t_idx].localColumn= t_idx.local[1];  
    });  
  
    // Print out the Description structure for each element in the matrix.  
    // Tiles are displayed in red and green to distinguish them from each other.  
    SetConsoleSize(100, 150);  
    for (int row = 0; row < ROWS; row++) {  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Value: " << std::setw(2) << descriptions(row, column).value << "      ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Tile:   " << "(" << descriptions(row, column).tileRow << "," << descriptions(row, column).tileColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Global: " << "(" << descriptions(row, column).globalRow << "," << descriptions(row, column).globalColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Local:  " << "(" << descriptions(row, column).localRow << "," << descriptions(row, column).localColumn << ")  ";  
        }  
        std::cout << "\n";  
        std::cout << "\n";  
    }  
}  
  
void main() {  
    TilingDescription();  
    char wait;  
    std::cin >> wait;  
}  
  
```  
  
 Le travail principal de l'exemple est dans la définition de l'objet `array_view` et l'appel à `parallel_for_each`.  
  
1.  Le vecteur des structures `Description` est copié dans un objet `array_view` 8x9.  
  
2.  La méthode `parallel_for_each` est appelée avec un objet `tiled_extent` comme domaine de calcul.  L'objet `tiled_extent` est créé en appelant la méthode `extent::tile()` de la variable `descriptions`.  Les types des paramètres de l'appel à `extent::tile()`, `<2,3>`, spécifient que des mosaïques 2x3 sont créées.  Par conséquent, la matrice 8x9 est disposée en mosaïque de 12 morceaux, quatre lignes et trois colonnes.  
  
3.  La méthode `parallel_for_each` est appelée à l'aide d'un objet `tiled_index<2,3>` \(`t_idx`\) comme index.  Les types des paramètres de l'index \(`t_idx`\) doivent correspondre aux types des paramètres du domaine de calcul \(`descriptions.extent.tile< 2, 3>()`\).  
  
4.  Lorsque chaque thread est exécuté, l'index, `t_idx`, retourne des informations sur quelle mosaïque contient le thread \(propriété`tiled_index::tile` \) et l'emplacement du thread dans la propriété \(`tiled_index::local` mosaïque\).  
  
## Synchronisation de mosaïque – tile\_static et tile\_barrier::wait  
 L'exemple précédent illustre la disposition et les index de la mosaïque, mais n'est pas fondamentalement très utile.  La mosaïque est utile lorsque les mosaïques sont intégrales à l'algorithme et exploitent les variables `tile_static`.  Comme tous les threads d'une mosaïque ont accès aux variables `tile_static`, les appels à `tile_barrier::wait` sont utilisés pour synchroniser l'accès aux variables `tile_static`.  Bien que tous les threads d'une mosaïque aient accès aux variables `tile_static`, il n'y a aucun ordre d'exécution des threads dans la mosaïque garanti.  L'exemple suivant montre comment utiliser des variables `tile_static` et la méthode `tile_barrier::wait` pour calculer la valeur moyenne de chaque mosaïque.  Voici les clés pour comprendre l'exemple :  
  
1.  Le rawData est stocké dans une matrice 8x8.  
  
2.  La taille de la mosaïque est 2x2.  Cela crée une grille de mosaïques 4x4 et les moyennes peuvent être stockées dans une matrice 4x4, à l'aide d'un objet `array`.  Il n'existe qu'un nombre limité de types que vous pouvez capturer par référence dans une fonction restreinte par AMP.  La classe `array` est l'une d'elles.  
  
3.  La taille de la matrice et la dimension de l'exemple sont définies à l'aide des instructions `#define`, car les paramètres de type de `array`, `array_view`, `extent`, et `tiled_index` doivent être des valeurs constantes.  Vous pouvez également utiliser des déclarations `const int static`.  Bénéfice supplémentaire, il est aisé de modifier la taille de l'exemple pour calculer la moyenne sur les mosaïques 4x4.  
  
4.  Un tableau `tile_static` 2x2 de valeurs float est déclaré pour chaque mosaïque.  Bien que la déclaration se trouve dans le chemin de code pour chaque thread, un seul tableau est créé pour chaque mosaïque de la matrice.  
  
5.  Il existe une ligne de code pour copier les valeurs de chaque mosaïque dan le tableau  `tile_static`.  Pour chaque thread, après que la valeur est copiée dans le tableau, l'exécution sur le thread s'arrête en raison de l'appel à `tile_barrier::wait`.  
  
6.  Lorsque tous les threads dans une mosaïque ont atteint le cloisonnement, la moyenne peut être calculée.  Comme le code s'exécute pour chaque thread, il existe une instruction `if` uniquement pour calculer la moyenne sur un thread.  La moyenne est stockée la variable des moyennes.  La barrière est essentiellement la construction qui contrôle les calculs par mosaïque, tout comme vous utiliseriez une boucle `for`.  
  
7.  Les données de la variable `averages`, car il s'agit d'un objet `array`, doivent être copiés vers l'hôte.  Cet exemple utilise l'opérateur de conversion vectoriel.  
  
8.  Dans l'exemple complet, vous pouvez changer SAMPLESIZE en 4 et le code s'exécute correctement sans aucune autre modification.  
  
```cpp  
  
#include <iostream>  
#include <amp.h>  
using namespace concurrency;  
  
#define SAMPLESIZE 2  
#define MATRIXSIZE 8  
void SamplingExample() {  
  
    // Create data and array_view for the matrix.  
    std::vector<float> rawData;  
    for (int i = 0; i < MATRIXSIZE * MATRIXSIZE; i++) {  
        rawData.push_back((float)i);  
    }  
    extent<2> dataExtent(MATRIXSIZE, MATRIXSIZE);  
    array_view<float, 2> matrix(dataExtent, rawData);  
  
    // Create the array for the averages.  
    // There is one element in the output for each tile in the data.  
    std::vector<float> outputData;  
    int outputSize = MATRIXSIZE / SAMPLESIZE;  
    for (int j = 0; j < outputSize * outputSize; j++) {  
        outputData.push_back((float)0);  
    }  
    extent<2> outputExtent(MATRIXSIZE / SAMPLESIZE, MATRIXSIZE / SAMPLESIZE);  
    array<float, 2> averages(outputExtent, outputData.begin(), outputData.end());  
  
    // Use tiles that are SAMPLESIZE x SAMPLESIZE.  
    // Find the average of the values in each tile.  
    // The only reference-type variable you can pass into the parallel_for_each call  
    // is a concurrency::array.  
    parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
         [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
    {  
        // Copy the values of the tile into a tile-sized array.  
        tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
        tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
        // Wait for the tile-sized array to load before you calculate the average.  
        t_idx.barrier.wait();  
  
        // If you remove the if statement, then the calculation executes for every  
        // thread in the tile, and makes the same assignment to averages each time.  
        if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
            for (int trow = 0; trow < SAMPLESIZE; trow++) {  
                for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
                }  
            }  
            averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
        }  
    });  
  
    // Print out the results.  
    // You cannot access the values in averages directly. You must copy them  
    // back to a CPU variable.  
    outputData = averages;  
    for (int row = 0; row < outputSize; row++) {  
        for (int col = 0; col < outputSize; col++) {  
            std::cout << outputData[row*outputSize + col] << " ";  
        }  
        std::cout << "\n";  
    }  
    // Output for SAMPLESSIZE = 2 is:  
    //  4.5  6.5  8.5 10.5  
    // 20.5 22.5 24.5 26.5  
    // 36.5 38.5 40.5 42.5  
    // 52.5 54.5 56.5 58.5  
  
    // Output for SAMPLESIZE = 4 is:  
    // 13.5 17.5  
    // 45.5 49.5  
}  
  
int main() {  
    SamplingExample();  
}  
  
```  
  
## Conditions de concurrence critique  
 Il peut être tentant d'essayer de créer une variable `tile_static` nommée `total` et d'incrémenter cette variable pour chaque thread, comme ceci :  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
total += matrix[t_idx];  
t_idx.barrier.wait();  
averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
  
```  
  
 Le premier problème avec cette approche est que les variables `tile_static` ne peuvent pas avoir d'initialiseurs.  Le second problème est qu'il existe une condition de concurrence critique sur l'assignation à `total`, car tous les threads de la mosaïque ont accès à la variable dans aucun ordre donné.  Vous pouvez programmer un algorithme pour ne permettre qu'à un seul thread d'accéder au total à chaque cloisonnement, comme indiqué dans l'exemple suivant.  Cette solution n'est, toutefois, pas extensible.  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
    total = matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
if (t_idx.local[0] == 0 && t_idx.local[1] == 1) {  
    total += matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
// etc.  
  
```  
  
## Frontières de mémoire  
 Il existe deux types d'accès mémoire qui doivent être synchronisés\- l'accès mémoire global et l'accès mémoire `tile_static`.  Un objet `concurrency::array` alloue seulement de la mémoire globale.  Un `concurrency::array_view` peut référencer la mémoire globale, la mémoire `tile_static` ou les deux, selon la façon dont elle a été développée.  Il existe deux types de mémoire qui doivent être synchronisés :  
  
-   mémoire globale  
  
-   `tile_static`  
  
 Une *barrière mémoire* garantit que les accès mémoire sont visibles par les autres threads de la mosaïque de threads et que les accès mémoire sont exécutés en fonction de l'ordre du programme.  Pour garantir cela, les compilateurs et les processeurs ne réorganisent pas les accès en lecture\/écriture à travers la barrière.  En C\+\+ AMP, une barrière mémoire est créée par un appel à l'une de ces méthodes :  
  
-   [tile\_barrier::wait, méthode](../Topic/tile_barrier::wait%20Method.md) : crée une frontière de sécurité autour de la mémoire globale et de la mémoire `tile_static`.  
  
-   [tile\_barrier::wait\_with\_all\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md) : crée une frontière de sécurité autour de la mémoire globale et de la mémoire `tile_static`.  
  
-   [tile\_barrier::wait\_with\_global\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md) : crée une frontière de sécurité uniquement autour de la mémoire globale.  
  
-   [tile\_barrier::wait\_with\_tile\_static\_memory\_fence, méthode](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md) : crée une frontière de sécurité autour uniquement de la mémoire  `tile_static`.  
  
 L'appel d'une délimitation spécifique dont vous avez besoin peut améliorer les performances de votre application.  Le type de barrière affecte la façon dont le compilateur et le matériel réorganisent les instructions.  Par exemple, si vous utilisez une frontière de sécurité globale de mémoire, elle s'applique uniquement aux accès mémoire globaux et par conséquent, le compilateur et le matériel peuvent réorganiser des lectures et des écritures dans les variables `tile_static` des deux côtés de la frontière de sécurité.  
  
 Dans l'exemple suivant, la barrière synchronise les écritures dans `tileValues`, une variable de `tile_static`.  Dans cet exemple, `tile_barrier::wait_with_tile_static_memory_fence` est appelée au lieu de `tile_barrier::wait`.  
  
```cpp  
  
// Using a tile_static memory fence.  
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
     [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
{  
    // Copy the values of the tile into a tile-sized array.  
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
    // Wait for the tile-sized array to load before calculating the average.  
    t_idx.barrier.wait_with_tile_static_memory_fence();  
  
    // If you remove the if statement, then the calculation executes for every  
    // thread in the tile, and makes the same assignment to averages each time.  
    if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
        for (int trow = 0; trow < SAMPLESIZE; trow++) {  
            for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
            }  
        }  
        averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
    }  
});  
  
```  
  
## Voir aussi  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [tile\_static, mot clé](../../cpp/tile-static-keyword.md)