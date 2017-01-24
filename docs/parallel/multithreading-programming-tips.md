---
title: "Multithreading&#160;: conseils de programmation | Microsoft Docs"
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
  - "contrôle d'accès (C++), multithreading"
  - "communications (C++), entre les threads"
  - "sections critiques (C++)"
  - "tables de handles (C++)"
  - "multithreading (C++), conseils de programmation"
  - "threads non MFC (C++)"
  - "objets (C++), threads multiples et"
  - "programmation (C++), multithread"
  - "synchronisation (C++), multithreading"
  - "threads (C++), meilleures pratiques"
  - "threads (MFC), conseils de programmation"
  - "dépanner (C++), multithreading"
  - "tables de handles Windows (C++)"
ms.assetid: ad14cc70-c91c-4c24-942f-13a75e58bf8a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading&#160;: conseils de programmation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications multithread demandent plus de vigilance que les applications à un seul thread lors de l'accès aux données.  Comme il existe plusieurs chemins d'exécution indépendants utilisés simultanément dans les applications multithread, les algorithmes, les données ou les deux doivent savoir que les données pourraient être utilisées par plusieurs threads à la fois.  Cette rubrique passe en revue les techniques permettant d'éviter les problèmes potentiels lors de la programmation d'applications multithread à l'aide de la bibliothèque MFC \(Microsoft Foundation Class\).  
  
-   [Accès aux objets à partir de plusieurs threads](#_core_accessing_objects_from_multiple_threads)  
  
-   [Accès aux objets MFC à partir de threads non\-MFC](#_core_accessing_mfc_objects_from_non.2d.mfc_threads)  
  
-   [Cartes de handles Windows](#_core_windows_handle_maps)  
  
-   [Communication inter\-thread](#_core_communicating_between_threads)  
  
##  <a name="_core_accessing_objects_from_multiple_threads"></a> Accès aux objets à partir de plusieurs threads  
 Pour des motifs tenant à la taille et à l'exécution, les objets MFC ne sont pas thread\-safe au niveau de l'objet, mais uniquement au niveau de la classe.  Ceci signifie que vous pouvez avoir deux threads distincts qui manipulent deux objets `CString` différents, mais pas deux threads manipulant le même objet `CString`.  Si vous devez absolument avoir plusieurs threads manipulant le même objet, protégez un tel accès à l'aide de mécanismes de synchronisation Win32 appropriés, comme les sections critiques.  Pour plus d'informations sur les sections critiques et d'autres objets apparentés, consultez [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 La bibliothèque des classes utilise les sections critiques en interne pour protéger les structures de données globales, telles que celles utilisées par l'allocation de mémoire de débogage.  
  
##  <a name="_core_accessing_mfc_objects_from_non.2d.mfc_threads"></a> Accès aux objets MFC à partir de threads non\-MFC  
 Si vous avez une application multithread qui crée un thread selon une méthode autre que l'utilisation d'un objet [CWinThread](../mfc/reference/cwinthread-class.md), vous ne pouvez pas accéder à d'autres objets MFC à partir de ce thread.  Autrement dit, si vous souhaitez accéder à un objet MFC à partir d'un thread secondaire, vous devez créer ce thread à l'aide de l'une des méthodes décrites dans [Multithreading : création de threads d'interface utilisateur](../parallel/multithreading-creating-user-interface-threads.md) ou [Multithreading : création de threads de travail](../parallel/multithreading-creating-worker-threads.md).  Ces méthodes sont les seules qui permettent à la bibliothèque des classes d'initialiser les variables internes nécessaires pour gérer des applications multithread.  
  
##  <a name="_core_windows_handle_maps"></a> Cartes de handles Windows  
 En règle générale, un thread peut accéder uniquement aux objets MFC qu'il crée.  Cela tient au fait que les cartes de handles Windows temporaires et permanents sont conservées dans le stockage local des threads afin de garantir leur protection contre l'accès simultané par plusieurs threads.  Par exemple, un thread de travail ne peut pas effectuer un calcul, puis appeler la fonction membre `UpdateAllViews` d'un document pour modifier les fenêtres contenant des vues des nouvelles données.  Ceci n'a aucun effet, car la carte des objets `CWnd` vers `HWND` est locale pour le thread principal.  Ceci signifie qu'un thread peut avoir un mappage à partir d'un handle Windows vers un objet C\+\+, mais un autre thread peut mapper le même handle vers un objet C\+\+ différent.  Les modifications effectuées dans un thread n'apparaîtraient pas dans l'autre.  
  
 Il existe différentes façons de contourner ce problème.  La première est de passer au thread de travail des handles \(par exemple, `HWND`\) à la place d'objets C\+\+.  Le thread de travail ajoute alors ces objets à sa carte temporaire en appelant la fonction membre `FromHandle` appropriée.  Vous pouvez également ajouter l'objet à la carte permanente du thread en appelant **Attach**, mais cela doit être effectué uniquement si vous avez la garantie que l'objet durera plus longtemps que le thread.  
  
 Une autre méthode consiste à créer de nouveaux messages définis par l'utilisateur correspondant aux différentes tâches que vos threads de travail exécuteront et distribuer ces messages à la fenêtre principale de l'application à l'aide de **::PostMessage**.  Ce mode de communication est similaire à celui de deux applications différentes qui dialoguent sauf que les deux threads s'exécutent dans le même espace d'adressage.  
  
 Pour plus d'informations sur ces cartes de handles, consultez [Technical Note 3](../mfc/tn003-mapping-of-windows-handles-to-objects.md).  Pour plus d'informations sur le stockage local des threads, consultez [Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686749) et [Using Thread Local Storage](http://msdn.microsoft.com/library/windows/desktop/ms686991) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
##  <a name="_core_communicating_between_threads"></a> Communication inter\-thread  
 MFC fournit un certain nombre de classes qui permettent aux threads de synchroniser l'accès aux objets afin de garantir leur propre sécurité.  L'utilisation de ces classes est décrite dans [Multithreading : comment utiliser les classes de synchronisation](../parallel/multithreading-how-to-use-the-synchronization-classes.md) et [Multithreading : quand utiliser les classes de synchronisation](../parallel/multithreading-when-to-use-the-synchronization-classes.md).  Pour plus d'informations sur ces objets, consultez [Synchronization](http://msdn.microsoft.com/library/windows/desktop/ms686353) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
## Voir aussi  
 [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md)