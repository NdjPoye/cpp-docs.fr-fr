---
title: "Proc&#233;dure pas-&#224;-pas&#160;: d&#233;bogage d’une application&#160;C++&#160;AMP | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "débogage, C++ Accelerated Massive Parallelism"
  - "C++ AMP, débogage"
  - "C++ Accelerated Massive Parallelism, débogage"
  - "débogage, C++ AMP"
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: 35
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas-&#224;-pas&#160;: d&#233;bogage d’une application&#160;C++&#160;AMP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment déboguer une application qui utilise le parallélisme massif accéléré par C\+\+ \(C\+\+ AMP\) pour tirer parti de l'unité de traitement des graphiques \(GPU\).  Il utilise un programme de réduction\-parallèle qui résume un grand tableau d'entiers.  Cette procédure pas à pas décrit les tâches suivantes :  
  
-   Lancement du débogueur du GPU.  
  
-   Inspecter les sous\-processus du GPU dans la fenêtre sous\-processus de GPU.  
  
-   Utiliser la fenêtre des piles parallèles pour observer simultanément les piles d'appels de plusieurs sous\-processus GPU.  
  
-   À l'aide de la fenêtre de traitements en parallèle pour inspecter des valeurs d'une expression unique sur plusieurs threads en même temps.  
  
-   Repérage, gel, dégel et regroupement des sous\-processus GPU.  
  
-   Exécuter tous les sous\-processus d'une tuile à un emplacement spécifique dans le code.  
  
## Composants requis  
 Avant de commencer cette visite :  
  
-   Lire [Présentation de C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md).  
  
-   Vérifiez que les numéros de lignes sont affichés dans l'éditeur de texte.  Pour plus d'informations, consultez [Comment : afficher les numéros de ligne dans l’Éditeur](../Topic/How%20to:%20Display%20Line%20Numbers%20in%20the%20Editor.md).  
  
-   Assurez \-vous que vous exécutez [!INCLUDE[win8](../../build/includes/win8_md.md)] ou [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] pour prendre en charge le débogage sur l'émulateur de logiciel.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### Pour créer l'exemple de projet  
  
1.  Démarrez Visual Studio.  
  
2.  Dans la barre de menus, sélectionnez **Fichier**, **Nouveau**, **Projet**.  
  
3.  Sous **Installé** dans le volet modèles, sélectionnez **Visual C\+\+**.  
  
4.  Choisissez **Application console Win32**, tapez `AMPMapReduce` dans la zone **Nom**, puis cliquez sur le bouton **OK**.  
  
5.  Choisissez le bouton **Suivant**.  
  
6.  Décochez la case **En\-tête précompilé**, puis choisissez le bouton **Terminer**.  
  
7.  Dans **Explorateur de solutions**, supprimer stdafx.h, targetver.h, et stdafx.cpp du projet.  
  
8.  Ouvrez AMPMapReduce.cpp et remplacez son contenu par le code suivant.  
  
    ```cpp  
  
    // AMPMapReduce.cpp defines the entry point for the program.  
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.   
  
    #include <stdio.h>  
    #include <tchar.h>  
    #include <amp.h>  
  
    const int BLOCK_DIM = 32;  
  
    using namespace concurrency;  
  
    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)  
    {  
        tile_static int localA[BLOCK_DIM];  
  
        index<1> globalIdx = t_idx.global * stride_size;  
        index<1> localIdx = t_idx.local;  
  
        localA[localIdx[0]] =  A[globalIdx];  
  
        t_idx.barrier.wait();  
  
        // Aggregate all elements in one tile into the first element.  
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)   
        {  
            if (localIdx[0] < i)   
            {  
  
                localA[localIdx[0]] += localA[localIdx[0] + i];  
            }  
  
            t_idx.barrier.wait();  
        }  
  
        if (localIdx[0] == 0)  
        {  
            A[globalIdx] = localA[0];  
        }  
    }  
  
    int size_after_padding(int n)  
    {  
        // The extent might have to be slightly bigger than num_stride to   
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.  
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)  
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;  
    }  
  
    int reduction_sum_gpu_kernel(array<int, 1> input)   
    {  
        int len = input.extent[0];  
  
        //Tree-based reduction control that uses the CPU.  
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)   
        {  
            // Number of useful values in the array, given the current  
            // stride size.  
            int num_strides = len / stride_size;    
  
            extent<1> e(size_after_padding(num_strides));  
  
            // The sum kernel that uses the GPU.  
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)  
            {  
                sum_kernel_tiled(idx, input, stride_size);  
            });  
        }  
  
        array_view<int, 1> output = input.section(extent<1>(1));  
        return output[0];  
    }  
  
    int cpu_sum(const std::vector<int> &arr) {  
        int sum = 0;  
        for (size_t i = 0; i < arr.size(); i++) {  
            sum += arr[i];  
        }  
        return sum;  
    }  
  
    std::vector<int> rand_vector(unsigned int size) {  
        srand(2011);  
  
        std::vector<int> vec(size);  
        for (size_t i = 0; i < size; i++) {  
            vec[i] = rand();  
        }  
        return vec;  
    }  
  
    array<int, 1> vector_to_array(const std::vector<int> &vec) {  
        array<int, 1> arr(vec.size());  
        copy(vec.begin(), vec.end(), arr);  
        return arr;  
    }  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
        std::vector<int> vec = rand_vector(10000);  
        array<int, 1> arr = vector_to_array(vec);  
  
        int expected = cpu_sum(vec);  
        int actual = reduction_sum_gpu_kernel(arr);  
  
        bool passed = (expected == actual);  
        if (!passed) {  
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);  
        }  
        printf("sum: %s\n", passed ? "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
    ```  
  
9. Dans la barre de menus, sélectionnez **Fichier**, **Enregistrer tout**.  
  
10. Dans **l'explorateur de solutions**, ouvrez le menu raccourci pour **AMPMapReduce**, et choisissez ensuite **Propriétés**.  
  
11. Dans la boîte de dialogue **Propriétés de pages**, sous **Propriétés de configuration**, choisissez **C\/C\+\+**, **En\-tête Précompilé**.  
  
12. Pour la propriété **En\-tête précompile**, sélectionnez **Ne pas utiliser d'En\-tête précompilé**, et choisissez ensuite le bouton **OK**.  
  
13. Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
## Déboguer le code du CPU  
 Dans cette procédure, vous utiliserez le débogueur Windows local pour vous assurer que le code du CPU dans cette application est correct.  Le segment de code CPU dans cette application qui est particulièrement intéressante est la boucle `for` dans la fonction `reduction_sum_gpu_kernel`.  Cela contrôle la réduction parallèle basé sur l'arbre qui est lancé sur le GPU.  
  
### Pour déboguer le code CPU  
  
1.  Dans **l'explorateur de solutions**, ouvrez le menu raccourci pour **AMPMapReduce**, et choisissez ensuite **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sous **Propriétés de configuration**, sélectionnez **Débogage**.  Vérifiez que **Débogueur local Windows** est sélectionné dans la liste **Débogueur à lancer**.  
  
3.  Retournez à l'éditeur de code.  
  
4.  Définissez les points d'arrêt sur les lignes de code indiquées dans l'illustration suivante \(environ lignes 67\-70\).  
  
     ![Points d'arrêt d'UC](../../parallel/amp/media/campcpubreakpoints.png "CampCpuBreakpoints")  
Points d'arrêt CPU  
  
5.  Dans la barre de menus, sélectionnez **Débogage**, puis **Démarrer le débogage**.  
  
6.  Dans la fenêtre **Locals**, observez la valeur pour `stride_size` jusqu'à ce que le point d'arrêt à la ligne 70 soit atteint.  
  
7.  Dans la barre de menus, choisissez **Débogage**, **Arrêter le débogage**.  
  
## Déboguer le code GPU  
 Cette section indique comment déboguer le code GPU, qui est le code contenu dans la fonction `sum_kernel_tiled`.  Le code GPU calcule la sum des entiers pour chaque ¨block¨ en parallèle.  
  
### Pour déboguer le code GPU  
  
1.  Dans **l'explorateur de solutions**, ouvrez le menu raccourci pour **AMPMapReduce**, et choisissez ensuite **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, sous **Propriétés de configuration**, sélectionnez **Débogage**.  
  
3.  Dans la liste **Débogueur à lancer**, sélectionnez **Débogueur Windows local**.  
  
4.  Dans la liste **Type de débogueur**, sélectionnez **GPU uniquement**.  
  
5.  Sélectionnez le bouton **OK**.  
  
6.  Mettez un point d'arrêt à la ligne 30, comme vous montre l'illustration suivante.  
  
     ![Points d'arrêt GPU](../../parallel/amp/media/campgpubreakpoints.png "CampGpuBreakpoints")  
Point d'arrêt GPU  
  
7.  Dans la barre de menus, sélectionnez **Débogage**, puis **Démarrer le débogage**.  Les points d'arrêt dans le code CPU aux lignes 67 et 70 ne sont pas exécutés pendant le débogage GPU car ces lignes de code sont exécutées sur le CPU.  
  
### Pour utiliser la fenêtre sous\-processus de GPU  
  
1.  Pour ouvrir la fenêtre des sous\-processus de GPU, dans la barre de menus, sélectionnez **Débogage**, **Windows**, **Sous\-Processus GPU**.  
  
     Vous pouvez inspecter l'état des sous\-processus GPU dans la fenêtre sous\-processus de GPU qui apparaît.  
  
2.  Ancrez la fenêtre sous\-processus de GPU en bas de Visual Studio.  Choisissez le bouton **Développez le commutateur de sous\-processus** pour afficher les tuiles et les zones de texte de sous\-processus.  La fenêtre sous\-processus GPU affiche le nombre total de sous\-processus GPU actifs et bloqués, comme indiqué dans l'illustration suivante.  
  
     ![Fenêtre Threads GPU avec 4 threads actifs](../../parallel/amp/media/campc.png "CampC")  
Fenêtre Threads GPU  
  
     Il y a 313 tuiles allouées pour ce calcul.  Chaque tuile comprend 32 sous\-processus.  Étant donné que le débogage local GPU se produit sur un émulateur logiciel, il existe quatre sous\-processus GPU actifs.  Les quatre sous\-processus exécutent les instructions simultanément et passent ensuite la valeur à l'instruction suivante.  
  
     Dans la fenêtre threads de GPU, il existe quatre threads de GPU actifs et 28 threads de GPU bloqués à l'instruction  [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) définie aux alentours de la ligne 21 \(`t_idx.barrier.wait();`\).  Les 32 sous\-processus GPU appartiennent à la première tuile, `tile[0]`.  Une flèche pointe vers la ligne qui inclut le sous\-processus actuel.  Pour basculer vers un sous\-processus différent, utilisez l'une des méthodes suivantes :  
  
    -   Dans la ligne pour le sous\-processus bascule vers la fenêtre des sous\-processus GPU, ouvrez le menu et choisissez **Basculer vers le sous\-processus**.  Si la ligne représente plusieurs sous\-processus, vous allez basculer au premier sous\-processus d'après les coordonnées de sous\-processus.  
  
    -   Entrez des tuiles et des valeurs de sous\-processus dans les zones de texte correspondantes puis sélectionnez le bouton **Basculer le sous\-processus**.  
  
     La fenêtre de la pile des appels affiche la pile des appels du sous\-processus actuel du GPU.  
  
### Pour utiliser la fenêtre de piles parallèles  
  
1.  Pour ouvrir la fenêtre Piles parallèle, dans la barre de menus, sélectionnez **Débogage**, **Windows**, **Piles parallèles**.  
  
     Vous pouvez utiliser la fenêtre piles parallèles pour inspecter simultanément les frames de pile de plusieurs sous\-processus GPU.  
  
2.  Ancrez la fenêtre Piles parallèles en bas de Visual Studio.  
  
3.  Assurez\-vous que **sous\-processus** est sélectionné dans la liste dans le coin supérieur gauche.  Dans l'illustration suivante, la fenêtre piles parallèles affiche une vue de la pile des appels concentrée sur les sous\-processus GPU que vous avez vu dans la fenêtre des sous\-processus GPU.  
  
     ![Fenêtre Piles parallèles avec 4 threads actifs](../../parallel/amp/media/campd.png "CampD")  
Fenêtre Piles parallèles  
  
     32 sous\-processus sont allés du `_kernel_stub` à l'instruction lambda dans l'appel de fonction `parallel_for_each` puis vers la fonction `sum_kernel_tiled`, où la réduction en parallèle se produit. 28 des 32 sous\-processus ont progressé à l'instruction de [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) et restent bloqués à la ligne 22, alors que les 4 autres sous\-processus restent actifs dans la fonction `sum_kernel_tiled` à la ligne 30.  
  
     Vous pouvez inspecter les propriétés d'un sous\-processus GPU disponibles dans la fenêtre sous\-processus GPU dans le rich DataTip de la fenêtre des piles parallèles.  Pour cela, maintenez le pointeur de la souris sur la pile de frame **sum\_kernel\_tiled**.  L'illustration suivante présente le DataTip.  
  
     ![DataTip pour la fenêtre Piles parallèles](../../parallel/amp/media/campe.png "CampE")  
Sous\-processus GPU DataTip  
  
     Pour plus d'informations sur la fenêtre piles parallèles, consultez [Utilisation de la fenêtre Piles parallèles](../Topic/Using%20the%20Parallel%20Stacks%20Window.md).  
  
### Pour utiliser la fenêtre Espion parallèle  
  
1.  Pour ouvrir la fenêtre Espion parallèle, dans la barre de menus, sélectionnez **Débogage**, **Windows**, **Espion parallèle**, **Espion parallèle 1**.  
  
     Vous pouvez utiliser la fenêtre Espion parallèle pour examiner les valeurs d'une expression entre les threads.  
  
2.  Ancrez la fenêtre Espion parallèle 1 en bas de Visual Studio.  Il existe 32 lignes dans la table de la fenêtre Espion parallèle.  Chacun correspond à un sous\-processus GPU qui apparait dans la fenêtre sous\-processus GPU et la fenêtre piles parallèles.  Maintenant, vous pouvez écrire des expressions que vous souhaitez inspecter entre chacun des 32 sous\-processus GPU.  
  
3.  Sélectionnez l'en\-tête de colonne **Ajouter un espion**, entrez `localIdx`, puis appuyez sur la touche ENTRÉE.  
  
4.  Sélectionnez l'en\-tête de colonne **Ajouter un espion** de nouveau, tapez `globalIdx`, puis appuyez sur la touche ENTRÉE.  
  
5.  Sélectionnez l'en\-tête de colonne **Ajouter un espion** de nouveau, tapez `localA[localIdx[0]]`, puis appuyez sur la touche ENTRÉE.  
  
     Vous pouvez trier par une expression spécifiée en sélectionnant son en\-tête de colonne correspondant.  
  
     Sélectionnez l'en\-tête de colonne **localA\[localIdx\[0\]\]** pour trier la colonne.  L'illustration suivante montre les résultats en triant par **localA\[localIdx\[0\]\]**.  
  
     ![Fenêtre Espion parallèle avec les résultats triés](../../parallel/amp/media/campf.png "CampF")  
 Résultats du tri  
  
     Vous pouvez exporter le contenu dans la fenêtre Espion parallèle vers Excel en choisissant le bouton Excel et en choisissant ensuite **Ouvrir dans Excel**.  Si vous avez Excel installé sur votre ordinateur de développement, cela ouvre une feuille de calcul Excel qui contient le contenu.  
  
6.  Dans le coin en haut à droite de la fenêtre d'Espion parallèle, il y a un contrôle de filtre que vous pouvez utiliser pour filtrer le contenu en utilisant des expressions Booléennes.  Entrez `localA[localIdx[0]] > 20000` dans la zone de texte de contrôle de filtre et choisissez la touche Entrée.  
  
     La fenêtre contient désormais uniquement les sous\-processus sur lesquels la valeur `localA[localIdx[0]]` est supérieure à 20000.  Le contenu est encore trié par la colonne `localA[localIdx[0]]`, qui est l'action de tri que vous avez précédemment effectué.  
  
## Signaler des sous\-processus de GPU  
 Vous pouvez marquer des threads GPU spécifiques en leur affectant des indicateurs dans la fenêtre Threads GPU, la fenêtre Espion parallèle, ou le DataTip dans la fenêtre Piles parallèles.  Si une ligne dans la fenêtre sous\-processus de GPU contient plusieurs sous\-processus, le marquage de cette ligne signale tous les sous\-processus qui sont contenus dans la ligne.  
  
### Pour signaler des sous\-processus de GPU  
  
1.  Sélectionnez l'en\-tête de colonne **\[Thread\]** dans la fenêtre espion parallèle de l'affiche 1 pour trier par l'index du titre et du sous\-processus de l'index.  
  
2.  Dans la barre de menus, sélectionnez **Débogage**, **Continuer**, qui provoque les quatre sous\-processus qui étaient actifs pour progresser vers le cloisonnement suivant \(défini à la ligne 32 d'AMPMapReduce.cpp\).  
  
3.  Sélectionnez le symbole de balise située sur le côté gauche de la ligne qui contient les quatre sous\-processus qui sont maintenant actif.  
  
     L'illustration suivante montre les quatre sous\-processus avec indicateur actifs dans la fenêtre sous\-processus de GPU.  
  
     ![Fenêtre Threads GPU avec threads avec indicateur](../../parallel/amp/media/campg.png "CampG")  
Threads actifs dans la fenêtre Threads GPU  
  
     La fenêtre Espion parallèle et le DataTip de la fenêtre piles parallèles indiquent tous les deux les sous\-processus avec indicateur.  
  
4.  Si vous souhaitez vous concentrer sur les quatre sous\-processus que vous marqué, vous pouvez sélectionner, dans les sous\-processus de GPU, l'affiche parallèles, et les fenêtres de piles parallèles, les sous\-processus avec indicateur uniquement.  
  
     Choisissez uniquement le bouton marqué par afficher dans toutes les fenêtres ou dans la barre d'outils **Emplacement de débogage**.  L'illustration suivante affiche uniquement le bouton marqué pour afficher dans la barre d'outils **Emplacement de débogage**.  
  
     ![Barre d'outils Emplacement de débogage avec icône Afficher uniquement avec indicateur](../../parallel/amp/media/camph.png "CampH")  
Bouton Afficher uniquement les threads avec indicateur  
  
     Maintenant les fenêtres des threads GPU, Espion parallèle et Piles parallèles n'affichent que les threads marqués.  
  
## Gel et libération des sous\-processus GPU  
 Vous pouvez figer \(en veille\) et libérer \(lors de la reprise\) des sous\-processus de GPU de la fenêtre sous\-processus de GPU ou de la fenêtre Espion parallèle.  Vous pouvez geler et libérer des sous\-processus CPU de la même façon ; pour plus d'informations, consultez [Comment : utiliser la fenêtre Threads](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
### Pour geler et libérer des sous\-processus de GPU  
  
1.  Cliquez sur le bouton d' **Affichez les marqués uniquement** pour afficher tous les sous\-processus.  
  
2.  Dans la barre de menus, choisissez **Déboguer**, **Continuer**.  
  
3.  Ouvrez le menu raccourci pour la ligne active et choisissez **Figer**.  
  
     L'illustration suivante de la fenêtre sous\-processus de GPU montre les quatre sous\-processus qui sont figés.  
  
     ![Fenêtres Threads GPU indiquant les threads figés](../../parallel/amp/media/campk.png "CampK")  
Threads figés dans la fenêtre Threads GPU  
  
     De même, la fenêtre Espion parallèle montre que les quatre sous\-processus sont figés.  
  
4.  Dans la barre de menus, sélectionnez **Débogage**, **Continuer** pour permettre aux quatre sous\-processus GPU suivants de progresser au\-delà du cloisonnement à la ligne 22 et pour atteindre le point d'arrêt à la ligne 30.  La fenêtre sous\-processus de GPU montre que les quatre threads précédemment figés restent figés et dans l'état actif.  
  
5.  Dans la barre de menus, choisissez **Déboguer**, **Continuer**.  
  
6.  De la fenêtre Espion parallèle, vous pouvez également libérer un ou plusieurs sous\-processus GPU.  
  
### Pour regrouper les threads GPU  
  
1.  Dans le menu contextuel pour un des sous\-processus dans la fenêtre **Sous\-processus GPU**, choisissez **Grouper par**, **Adresse**.  
  
     Les sous\-processus dans la fenêtre sous\-processus GPU sont regroupés par adresse.  L'adresse correspond à l'instruction dans le code machine où chaque groupe de sous\-processus se trouve. 24 threads sont à la ligne 22 où la [tile\_barrier::wait, méthode](../Topic/tile_barrier::wait%20Method.md) est exécutée. 12 sous\-processus sont à l'instruction pour le cloisonnement à la ligne 32.  Quatre de ces sous\-processus sont marqués d'un indicateur.  Huit sous\-processus sont au point d'arrêt à la ligne 30.  Quatre de ces sous\-processus sont figés.  L'illustration suivante montre les sous\-processus regroupés dans la fenêtre sous\-processus de GPU.  
  
     ![Fenêtre Threads GPU avec threads groupés par adresse](../../parallel/amp/media/campl.png "CampL")  
Les sous\-processus regroupés dans la fenêtre sous\-processus GPU  
  
2.  Vous pouvez également exécuter l'opération **Grouper par** en ouvrant le menu contextuel pour la grille de données de la fenêtre Espion parallèle, choisir **Grouper par**, puis choisir l'élément de menu qui correspond à la façon dont vous souhaitez grouper les sous\-processus.  
  
## Exécuter tous les sous\-processus à un emplacement spécifique dans le code  
 Vous exécutez tous les threads dans une mosaïque donnée à la ligne qui contient le curseur à l'aide de **Exécuter le tile actuel au curseur**.  
  
### Pour exécuter tous les sous\-processus à l'emplacement marqué par le curseur  
  
1.  Dans le menu contextuel pour les sous\-processus figés, choisissez **Libérer**.  
  
2.  Dans l'éditeur de code, mettez le curseur à la ligne 30.  
  
3.  Sur le menu raccourci pour l'éditeur de code, choisissez **Exécuter la mosaïque actuelle au curseur**.  
  
     Les 24 threads qui ont été précédemment bloqués au cloisonnement à la ligne 21 ont progressés pour à la ligne 32.  Cela est indiqué dans la fenêtre **Threads GPU**.  
  
## Voir aussi  
 [Présentation de C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md)   
 [Débogage du code GPU](../Topic/Debugging%20GPU%20Code.md)   
 [Comment : utiliser la fenêtre Threads GPU](../Topic/How%20to:%20Use%20the%20GPU%20Threads%20Window.md)   
 [Comment : utiliser la fenêtre Espion parallèle](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)   
 [Analyse de code C\+\+ AMP avec le visualiseur concurrentiel](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)