---
title: "&#201;criture d&#39;un programme Win32 multithread | Microsoft Docs"
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
helpviewer_keywords: 
  - "communications (C++), entre les threads"
  - "multithreading (C++), partager des ressources communes"
  - "multithreading (C++), piles des threads"
  - "mutex (C++)"
  - "mutex (C++)"
  - "ressources (C++), multithreading"
  - "ressources partagées (C++)"
  - "piles (C++)"
  - "piles des threads (C++)"
  - "threads (C++), partager des ressources communes"
  - "threads (C++), piles des threads"
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;criture d&#39;un programme Win32 multithread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous incorporez de multiples threads dans un programme que vous écrivez, vous devez coordonner leur comportement et [utilisation des ressources du programme](#_core_sharing_common_resources_between_threads).  Vous devez également vous assurer que chaque thread reçoit sa [propre pile](#_core_thread_stacks).  
  
##  <a name="_core_sharing_common_resources_between_threads"></a> Partage de ressources communes entre les threads  
  
> [!NOTE]
>  Pour une description similaire sous l'angle MFC, consultez [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md) et [Multithreading : quand utiliser les classes de synchronisation](../parallel/multithreading-when-to-use-the-synchronization-classes.md).  
  
 Chaque thread possède sa propre pile et sa propre copie des registres de l'UC.  Les autres ressources, telles que les fichiers, les données statiques et le tas, sont partagées par tous les threads du processus.  Les threads utilisant ces ressources communes doivent être synchronisés.  Win32 propose plusieurs méthodes de synchronisation des ressources, notamment au moyen des sémaphores, des sections critiques, des événements et des mutex.  
  
 Quand plusieurs threads accèdent à des données statiques, votre programme doit prévoir les conflits de ressources possibles.  Considérons un programme où un thread met à jour une structure de données statiques contenant les coordonnées *x*, *y* pour des éléments devant être affichés par un autre thread.  Si le thread de mise à jour modifie la coordonnée *x* et est interrompu avant d'avoir modifié la coordonnée *y*, le thread d'affichage risque d'être planifié avant la mise à jour de la coordonnée *y*.  L'élément ne serait pas affiché à l'emplacement approprié.  Pour éviter ce problème, il suffit d'utiliser des sémaphores pour contrôler l'accès à la structure.  
  
 Un mutex \(de *mutual ex*clusion ou *exclusion mutuelle*\) est un mode de communication entre les threads ou les processus qui s'exécutent les uns les autres de manière asynchrone.  Cette communication est en principe utilisée pour coordonner les activités de plusieurs threads ou processus, en contrôlant de façon générale l'accès à une ressource partagée par le verrouillage et le déverrouillage de la ressource.  Pour résoudre ce problème de mise à jour de coordonnées *x*, *y*, le thread de mise à jour doit définir un mutex indiquant que la structure de données est en cours d'utilisation avant d'exécuter la mise à jour.  Il doit aussi supprimer le mutex une fois les deux coordonnées traitées.  Le thread d'affichage doit attendre que le mutex ait été supprimé avant de mettre à jour l'affichage.  Ce processus d'attente d'un mutex est souvent désigné par le terme « blocage » sur un mutex car le processus est bloqué et ne peut pas continuer tant que le mutex n'a pas été supprimé.  
  
 Le programme Bounce.c affiché dans les utilisations [Exemple de programme multithread en langage C](../parallel/sample-multithread-c-program.md) utilise un mutex nommé `ScreenMutex` pour coordonner les mises à jour de l'écran.  Chaque fois que l'un des threads d'affichage est prêt à écrire vers l'écran, il appelle **WaitForSingleObject** avec le handle de `ScreenMutex` et la constante **INFINITE** pour indiquer que l'appel **WaitForSingleObject** doit effectuer un blocage sur le mutex et ne pas expirer.  Si `ScreenMutex` est supprimé, la fonction d'attente définit le mutex de sorte que d'autres threads ne puissent pas interférer avec l'affichage et continue d'exécuter le thread.  Sinon, le thread se bloque jusqu'à la disparition du mutex.  Lorsque le thread termine la mise à jour de l'affichage, il libère le mutex en appelant **ReleaseMutex**.  
  
 Les affichages d'écran et les données statiques sont les deux seules ressources qui exigent une gestion attentive.  Par exemple, votre programme peut avoir plusieurs threads qui accèdent au même fichier.  Comme un autre thread peut avoir déplacé le pointeur du fichier, chaque thread doit redéfinir le pointeur de fichier avant toute opération de lecture ou d'écriture.  De plus, chaque thread doit faire en sorte qu'il ne soit pas interrompu entre le moment où il positionne le pointeur et le moment où il accède au fichier.  Ces threads doivent utiliser un sémaphore pour coordonner l'accès au fichier en délimitant chaque accès de fichier par des appels de **WaitForSingleObject** et **ReleaseMutex**.  L'exemple de code suivant illustre cette technique :  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a> Piles des threads  
 Tout l'espace de pile par défaut d'une application est alloué au premier thread d'exécution qui est appelé thread 1.  Par conséquent, vous devez spécifier la quantité de mémoire à allouer pour une pile séparée pour chaque thread supplémentaire que nécessite votre programme.  Le système d'exploitation alloue, le cas échéant, un espace de pile supplémentaire au thread, mais vous devez spécifier une valeur par défaut.  
  
 Le premier argument dans l'appel de `_beginthread` est un pointeur désignant la fonction **BounceProc**, qui exécute les threads.  Le deuxième argument spécifie la taille de la pile par défaut du thread.  Le dernier argument est un numéro d'ID qui est passé à **BounceProc**.  **BounceProc** utilise le numéro d'ID pour amorcer le générateur de nombres aléatoires et sélectionner l'attribut couleur et le caractère d'affichage du thread.  
  
 Les threads qui adressent des appels à la bibliothèque Runtime C ou à l'API Win32 doivent prévoir un espace de pile suffisant pour la bibliothèque et les fonctions API qu'ils appellent.  La fonction `printf` du C exige plus de 500 octets d'espace pile, et vous devez disposer de 2 Ko d'espace de pile lorsque vous appelez des routines de l'API Win32.  
  
 Dans la mesure où chaque thread possède sa propre pile, vous pouvez éviter les collisions potentielles au niveau des éléments de données en utilisant aussi peu de données statiques que possible.  Concevez votre programme de façon à utiliser des variables de pile automatiques pour toutes les données pouvant être exclusives à un thread.  Les seules variables globales du programme Bounce.c sont soit les mutex soit les variables qui ne changent jamais une fois initialisées.  
  
 Win32 fournit également un stockage local des threads \(TLS, Thread\-Local Storage\) pour le stockage des données par thread.  Pour plus d'informations, consultez [Stockage local des threads \(TLS\)](../parallel/thread-local-storage-tls.md).  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)