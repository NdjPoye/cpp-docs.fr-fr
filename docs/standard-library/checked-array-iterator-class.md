---
title: "checked_array_iterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/checked_array_iterator"
  - "checked_array_iterator"
  - "std::checked_array_iterator"
  - "std.checked_array_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked_array_iterator"
  - "checked_array_iterator (classe)"
  - "checked_array_iterator, syntaxe"
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# checked_array_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `checked_array_iterator` vous permet de transformer un tableau ou un pointeur en un itérateur vérifié.  Utilisez cette classe comme wrapper \(à l'aide de la fonction [make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)\) pour les pointeurs ou tableaux bruts en tant que moyen ciblé d'exécuter des vérifications et de gérer les avertissements de pointeur non vérifiés, au lieu de désactiver globalement ces avertissements.  Si nécessaire, utilisez la version non vérifiée de cette classe : [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md).  
  
> [!NOTE]
>  Cette classe est une extension Microsoft de la bibliothèque C\+\+ standard.  Le code implémenté à l'aide de cette fonction ne peut pas être utilisé dans les environnements de build C\+\+ standard qui ne prennent pas en charge cette extension Microsoft.  Pour savoir comment écrire du code qui ne requiert pas l'utilisation de cette classe, consultez le deuxième exemple ci\-dessous.  
  
## Syntaxe  
  
```  
template <class _Iterator>  
    class checked_array_iterator;  
```  
  
## Notes  
 Cette classe est définie dans l'espace de noms [stdext](../standard-library/stdext-namespace.md).  
  
 Pour plus d'informations et pour obtenir un exemple de code sur la fonctionnalité d'itérateur vérifié, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## Exemple  
 L'exemple suivant indique comment définir et utiliser un itérateur vérifié de tableau.  
  
 Si la destination n'est pas suffisamment grande pour contenir tous les éléments copiés, ce qui serait le cas si vous aviez modifié la ligne suivante :  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
```  
  
 à  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));  
```  
  
 Une erreur d'exécution se produira.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
```  
  
  **\( 0 1 2 3 4 \)**  
**\( 0 1 2 3 4 \)**   
## Exemple  
 Pour éviter d'avoir besoin de la classe `checked_array_iterator` lorsque vous utilisez des algorithmes de bibliothèque C\+\+ standard, utilisez un `vector` au lieu d'un tableau alloué dynamiquement.  L'exemple suivant illustre la procédure à suivre pour réaliser cette opération.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
### Constructeurs  
  
|||  
|-|-|  
|[checked\_array\_iterator](../Topic/checked_array_iterator::checked_array_iterator.md)|Construit un `checked_array_iterator` par défaut ou un `checked_array_iterator` à partir d'un itérateur sous\-jacent.|  
  
### Typedefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/checked_array_iterator::difference_type.md)|Type qui fournit la différence entre deux objets `checked_array_iterator` se rapportant à des éléments dans le même conteneur.|  
|[pointer](../Topic/checked_array_iterator::pointer.md)|Type qui fournit un pointeur vers un élément traité par un `checked_array_iterator`.|  
|[reference](../Topic/checked_array_iterator::reference.md)|Type qui fournit une référence à un élément traité par un `checked_array_iterator`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[base](../Topic/checked_array_iterator::base.md)|Récupère l'itérateur sous\-jacent à partir de son `checked_array_iterator`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\=\=](../Topic/checked_array_iterator::operator==.md)|Vérifie si deux objets `checked_array_iterator` sont égaux.|  
|[operator\!\=](../Topic/checked_array_iterator::operator!=.md)|Vérifie si deux objets `checked_array_iterator` sont inégaux.|  
|[operator\<](../Topic/checked_array_iterator::operator%3C.md)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur au `checked_array_iterator` du côté droit.|  
|[operator\>](../Topic/checked_array_iterator::operator%3E.md)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur à l'objet `checked_array_iterator` du côté droit.|  
|[operator\<\=](../Topic/checked_array_iterator::operator%3C=.md)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est inférieur ou égal au `checked_array_iterator` du côté droit.|  
|[operator\>\=](../Topic/checked_array_iterator::operator%3E=.md)|Vérifie si le `checked_array_iterator` à gauche de l'opérateur est supérieur ou égal au `checked_array_iterator` du côté droit.|  
|[operator\*](../Topic/checked_array_iterator::operator*.md)|Retourne l'élément traité par `checked_array_iterator`.|  
|[operator\-\>](../Topic/checked_array_iterator::operator-%3E.md)|Retourne un pointeur vers l'élément traité par le `checked_array_iterator`.|  
|[operator\+\+](../Topic/checked_array_iterator::operator++.md)|Incrémente le `checked_array_iterator` à l'élément suivant.|  
|[operator\-\-](../Topic/checked_array_iterator::operator--.md)|Décrémente le `checked_array_iterator` à l'élément précédent.|  
|[operator\+\=](../Topic/checked_array_iterator::operator+=.md)|Ajoute un décalage spécifié à un `checked_array_iterator`.|  
|[operator\+](../Topic/checked_array_iterator::operator+.md)|Ajoute un décalage à un itérateur et retourne le nouvel `checked_array_iterator` qui se rapporte à l'élément inséré à la nouvelle position décalée.|  
|[operator\-\=](../Topic/checked_array_iterator::operator-=.md)|Décrémente un décalage spécifié d'un `checked_array_iterator`.|  
|[operator\-](../Topic/checked_array_iterator::operator-.md)|Décrémente un décalage depuis un itérateur et retourne le nouveau `checked_array_iterator` qui traite l'élément inséré à la nouvelle position décalée.|  
|[operator&#91;&#93;](../Topic/checked_array_iterator::operator.md)|Retourne une référence à un élément décalé d'un nombre donné de positions par rapport à l'élément auquel un `checked_array_iterator` se rapportait.|  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)