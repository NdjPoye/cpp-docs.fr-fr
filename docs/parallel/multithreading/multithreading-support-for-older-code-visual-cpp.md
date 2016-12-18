---
title: "Prise en charge du multithreading pour le code plus ancien (Visual C++) | Microsoft Docs"
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
  - "programmation simultanée (C++)"
  - "plusieurs threads simultanés"
  - "threads multiples"
  - "multithreading (C++)"
  - "multithreading (C++), à propos du multithreading (C++)"
  - "programmation (C++), multithread"
  - "threads (C++)"
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge du multithreading pour le code plus ancien (Visual C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ permet l'utilisation simultanée de plusieurs threads d'exécution concurrents.  Grâce au multithreading, vous pouvez exécuter des tâches d'arrière\-plan, traiter des flux simultanés d'entrées utilisateur, gérer une interface utilisateur, et bien plus.  
  
## Dans cette section  
 [Multithreading à l'aide de C et de Win32](../../parallel/multithreading-with-c-and-win32.md)  
 Fournit la prise en charge nécessaire pour créer des applications multithread avec Microsoft Windows.  
  
 [Multithreading à l'aide de C\+\+ et de MFC](../../parallel/multithreading-with-cpp-and-mfc.md)  
 Explique ce que sont les processus et les threads, ainsi que l'approche MFC en matière de multithreading.  
  
 [Multithreading et paramètres régionaux](../../parallel/multithreading-and-locales.md)  
 Traite des problèmes qui surviennent lors de l'utilisation des fonctionnalités de paramètres régionaux de la bibliothèque Runtime C et de la bibliothèque C\+\+ standard dans une application multithread.  
  
## Rubriques connexes  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
 Représente un thread d'exécution dans une application.  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
 Décrit une classe virtuelle pure qui fournit une fonctionnalité commune aux objets de synchronisation dans Win32.  
  
 [CSemaphore](../../mfc/reference/csemaphore-class.md)  
 Représente un sémaphore, un objet de synchronisation qui permet à un nombre limité de threads dans un ou plusieurs processus d'accéder à une ressource.  
  
 [CMutex](../../mfc/reference/cmutex-class.md)  
 Représente un mutex, un objet de synchronisation qui permet à un thread l'accès mutuellement exclusif à une ressource.  
  
 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)  
 Représente une section critique, un objet de synchronisation qui permet à un seul thread à la fois l'accès à une ressource ou à une section du code.  
  
 [CEvent](../../mfc/reference/cevent-class.md)  
 Représente un event, un objet de synchronisation qui permet à un thread de notifier à un autre thread qu'un événement s'est produit.  
  
 [CMultiLock](../../mfc/reference/cmultilock-class.md)  
 Représente le mécanisme de contrôle d'accès utilisé pour accéder aux ressources dans un programme multithread.  
  
 [CSingleLock](../../mfc/reference/csinglelock-class.md)  
 Représente le mécanisme de contrôle d'accès utilisé dans le contrôle de l'accès à une ressource dans un programme multithread.  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/fr-fr/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Fournit des liens vers des rubriques qui fournissent des informations conceptuelles sur les bibliothèques Visual C\+\+ et des rubriques qui traitent des différentes technologies et techniques de codage.