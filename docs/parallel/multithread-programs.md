---
title: "Programmes multithread | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multithreading (C++), à propos des threads"
  - "threads (C++), à propos du threading"
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Programmes multithread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un thread est un chemin d'exécution au sein d'un programme.  Il s'agit également de la plus petite unité d'exécution planifiée par l'interface Win32.  Chaque thread est composé d'une pile, de l'état des registres de l'UC et d'une entrée dans la liste d'exécution du planificateur système.  Les ressources du processus sont partagées par tous les threads.  
  
 Un processus contient un ou plusieurs threads ainsi que le code, les données et d'autres ressources d'un programme en mémoire.  Les ressources types d'un programme sont les fichiers ouverts, les sémaphores et la mémoire allouée dynamiquement.  Le programme s'exécute quand le planificateur système transmet un ordre d'exécution à l'un de ses threads.  C'est le planificateur qui détermine quels threads doivent s'exécuter et quand ils doivent le faire.  Les threads d'un niveau de priorité inférieur doivent attendre que les threads de niveau de priorité supérieur aient terminé leurs tâches.  Sur les ordinateurs multiprocesseurs, le planificateur peut répartir les threads entre les différents processeurs afin d'équilibrer la charge de l'UC.  
  
 Chaque thread d'un processus fonctionne de manière indépendante.  À moins de les rendre visibles les uns aux autres, les threads s'exécutent individuellement et ignorent tout des autres threads présents au sein du processus.  Les threads qui partagent des ressources communes doivent, cependant, coordonner leur travail en utilisant des sémaphores ou une autre méthode de communication interprocessus.  Pour plus d'informations sur la synchronisation des threads, consultez [Écriture d'un programme Win32 multithread](../parallel/writing-a-multithreaded-win32-program.md).  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)