---
title: "Classes de prise en charge des applications et des threads | Microsoft Docs"
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
  - "vc.classes.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets application (C++), classes de prise en charge des threads"
  - "classes de prise en charge des applications (C++)"
  - "classes de verrouillage"
  - "classes de synchronisation, multithreading"
  - "classes de prise en charge des threads (C++)"
  - "threads (MFC)"
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de prise en charge des applications et des threads
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque application possède un seul objet d'application ; cet objet coordonne d'autres objets dans le programme en cours de exécution et est dérivé de `CWinApp`.  
  
 La bibliothèque Microsoft Foundation Class \(MFC\) prend en charge des threads d'exécution multiples dans une application.  Toutes les applications doivent avoir au moins un thread ; le thread utilisé par votre objet `CWinApp` est ce thread principal.  
  
 `CWinThread` encapsule une partie des fonctions de threading du système d'exploitation.  Pour faciliter l'utilisation des threads, MFC fournit également des classes d'objets de synchronisation pour fournir une interface C\+\+ aux objets de synchronisation Win32.  
  
## Classes d'application et de thread  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 Encapsule le code pour initialiser, exécuter, et interrompre l'application.  Vous dériverez votre objet d'application de la classe.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 La classe de base pour tous les threads.  Utilisez directement, ou dérivez une classe de `CWinThread` si le thread remplit les fonctions d'interface utilisateur.  `CWinApp` est dérivé de `CWinThread`.  
  
## Classes d'objets de synchronisation  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 Classe de base pour les classes d'objets de synchronisation.  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 Une classe de synchronisation qui permet à un seul thread dans un seul processus d'accéder à un objet.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 Une classe de synchronisation qui permet entre un et un nombre maximal spécifié d'accès simultanés à un objet.  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 Une classe de synchronisation qui permet à un seul thread dans un nombre quelconque de processus d'accéder à un objet.  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 Une classe de synchronisation qui notifie une application lorsqu'un événement s'est produit.  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 Utilisé dans les méthodes des classes thread\-safe pour verrouiller sur un objet de synchronisation.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 Utilisé dans les méthodes des classes thread\-safe pour verrouiller sur un ou plusieurs objets de synchronisation d'un tableau d'objets de synchronisation.  
  
## Classes liées  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 Analyse la ligne de commande avec laquelle votre programme a démarré.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 Place un curseur d'attente à l'écran.  Utilisé durant les opérations prolongées.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 Gère le stockage permanent des données d'état d'ancrage des barres de contrôle.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 Contient la liste des fichiers récemment utilisés \(MRU\).  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)