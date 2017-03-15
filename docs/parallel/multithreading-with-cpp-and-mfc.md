---
title: "Multithreading &#224; l&#39;aide de C++ et de MFC | Microsoft Docs"
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
  - "CWinThread (classe), rôle de"
  - "MFC (C++), multithreading"
  - "multithreading (C++), MFC"
  - "synchronisation (C++), multithreading"
  - "classes de synchronisation (C++)"
  - "threads (C++), MFC"
  - "threads (MFC)"
  - "threads (MFC), à propos du threading"
  - "threads de l'interface utilisateur (C++)"
  - "threads de travail (C++)"
ms.assetid: 979605f8-3988-44b5-ac9c-b8cce7fcce14
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading &#224; l&#39;aide de C++ et de MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC \(Microsoft Foundation Class\) prend en charge les applications multithread.  Cette rubrique explique ce que sont les processus et les threads, ainsi que l'approche MFC en matière de multithreading.  
  
 Un processus est une instance d'exécution d'une application.  Par exemple, lorsque vous double\-cliquez sur l'icône Bloc\-notes, vous démarrez un processus qui exécute le Bloc\-notes.  
  
 Un thread est un chemin d'exécution au sein d'un processus.  Lorsque vous lancez le Bloc\-notes, le système d'exploitation crée un processus et commence l'exécution du thread principal de ce processus.  Le processus prend fin en même temps que le thread.  Ce thread principal est fourni au système d'exploitation par le code de démarrage sous la forme d'une adresse de fonction.  En principe, il s'agit de l'adresse de la fonction **main** ou `WinMain`.  
  
 Vous pouvez, le cas échéant, créer des threads supplémentaires dans votre application.  Ce peut être le cas si vous voulez gérer des tâches d'arrière\-plan ou de maintenance et que vous ne souhaitiez pas que l'utilisateur attende la fin de leur exécution.  Tous les threads des applications MFC sont représentés par des objets [CWinThread](../mfc/reference/cwinthread-class.md).  Dans la plupart des situations, il n'est même pas nécessaire de créer explicitement ces objets ; il suffit d'appeler la fonction d'aide de la structure [AfxBeginThread](../Topic/AfxBeginThread.md), qui crée l'objet `CWinThread` pour vous.  
  
 MFC distingue deux types de threads : les threads d'interface utilisateur et les threads de travail.  Les threads d'interface utilisateur sont généralement utilisés pour gérer les entrées effectuées par l'utilisateur et répondre aux événements et messages générés par ce même utilisateur.  Les threads de travail sont généralement utilisés pour l'exécution de tâches, telles que le recalcul, qui ne requièrent pas une entrée d'utilisateur.  L'API Win32 ne fait pas de différence entre les types de threads ; elle a juste besoin de connaître l'adresse de début du thread afin qu'elle puisse commencer à l'exécuter.  MFC gère spécialement des threads d'interface utilisateur en fournissant une pompe de messages pour les événements dans l'interface utilisateur.  `CWinApp` est un exemple d'un objet de thread d'interface utilisateur, parce qu'il dérive de `CWinThread` et gère des événements et des messages générés par l'utilisateur.  
  
 Une attention particulière doit être portée aux situations où plusieurs threads peuvent requérir l'accès au même objet.  [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md) décrit les techniques permettant d'éviter les incidents auxquels ces situations peuvent donner lieu.  [Multithreading : comment utiliser les classes de synchronisation](../parallel/multithreading-how-to-use-the-synchronization-classes.md) explique comment utiliser les classes disponibles pour synchroniser l'accès de plusieurs threads au même objet.  
  
 L'écriture et le débogage de programmes multithread représentent par nature une entreprise complexe et épineuse, dans la mesure où vous devez faire en sorte que les objets ne soient disponibles que pour un thread à la fois.  Les rubriques de multithreading n'abordent pas les notions élémentaires de la programmation multithread, mais seulement la façon d'utiliser MFC dans un programme multithread.  Les exemples multithread MFC, inclus dans Visual C\+\+, illustrent quelques interfaces Adding Functionality et API Win32 multithread non comprises dans la bibliothèque MFC ; cependant, ils ne constituent qu'un point de départ.  
  
 Pour plus d'informations sur la façon dont le système d'exploitation gère les processus et les threads, consultez [Processus et threads](http://msdn.microsoft.com/library/windows/desktop/ms684841), dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Pour plus d'informations sur la prise en charge du multithreading par MFC, consultez les rubriques suivantes :  
  
-   [Multithreading : création de threads d'interface utilisateur](../parallel/multithreading-creating-user-interface-threads.md)  
  
-   [Multithreading : création de threads de travail](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Multithreading : comment utiliser les classes de synchronisation](../parallel/multithreading-how-to-use-the-synchronization-classes.md)  
  
-   [Multithreading : arrêt d'exécution des threads](../parallel/multithreading-terminating-threads.md)  
  
-   [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md)  
  
-   [Multithreading : quand utiliser les classes de synchronisation](../parallel/multithreading-when-to-use-the-synchronization-classes.md)  
  
## Voir aussi  
 [Prise en charge du multithreading pour le code plus ancien \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)