---
title: "Multithreading &#224; l&#39;aide de&#160;C et de Win32 | Microsoft Docs"
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
  - "multithreading (C++), C et Win32"
  - "threads (C)"
  - "threads (C++), C et Win32"
  - "Visual C, multithreading"
  - "Win32 (C++), multithreading"
  - "applications Win32 (C++), multithreading"
  - "API Windows (C++), multithreading"
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreading &#224; l&#39;aide de&#160;C et de Win32
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ fournit une prise de en charge pour la création d'applications multithread avec Microsoft Windows : Windows XP, Windows 2000, Windows NT, Windows Millenium Edition et Windows 98.  Vous devez envisager d'utiliser plusieurs threads si votre application doit gérer plusieurs activités, telles que les entrées simultanées du clavier et de la souris.  Un thread peut traiter les entrées saisies au clavier pendant qu'un autre thread filtre les activités de la souris.  Un troisième thread peut actualiser l'écran d'affichage en fonction des données provenant des threads du clavier et de la souris.  Parallèlement, d'autres threads peuvent accéder aux fichiers sur le disque ou obtenir des données à partir d'un port de communication.  
  
 Visual C\+\+ propose deux modes de programmation avec les threads multiples, à l'aide de la bibliothèque MFC \(Microsoft Foundation Class\) ou de la bibliothèque Runtime C et de l'API Win32.  Pour plus d'informations sur la création d'applications multithread à l'aide de MFC, consultez [Multithreading à l'aide de C\+\+ et de MFC](../parallel/multithreading-with-cpp-and-mfc.md) après avoir pris connaissance des présentes rubriques consacrées au multithreading en langage C.  
  
 Cette série de rubriques décrit les fonctions de Visual C\+\+ qui prennent en charge la création de programmes multithread.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [La notion de multithreading](../parallel/multithread-programs.md)  
  
-   [Bibliothèques de prise en charge du multithreading](../parallel/library-support-for-multithreading.md)  
  
-   [Fichiers Include pour le multithreading](../parallel/include-files-for-multithreading.md)  
  
-   [Fonctions des bibliothèques Runtime C pour le contrôle des threads](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [Exemple de programme multithread en langage C](../parallel/sample-multithread-c-program.md)  
  
-   [Écriture d'un programme Win32 multithread](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [Compilation et liaison de programmes multithread](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [Comment éviter les sources d'incident dans les programmes multithread](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [Stockage local des threads](../parallel/thread-local-storage-tls.md)  
  
## Voir aussi  
 [Prise en charge du multithreading pour le code plus ancien \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)