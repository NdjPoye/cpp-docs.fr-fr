---
title: "4. Environment Variables | Microsoft Docs"
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
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4. Environment Variables
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce chapitre des variables d'environnement décrit OpenMP C et C\+\+ API \(ou des mécanismes spécifiques à la plateforme équivalents\) qui contrôle l'exécution du code parallèle.  les noms des variables d'environnement doivent être majuscules.  Les valeurs assignées à ces derniers ne respectent pas la casse et peuvent posséder l'espace blanc de début et de fin.  Les modifications apportées aux valeurs une fois que le programme a démarré sont ignorées.  
  
 Les variables d'environnement :  
  
-   **OMP\_SCHEDULE** définit le type et la taille du segment d'exécution de planification.  
  
-   **OMP\_NUM\_THREADS** définit le nombre de threads à utiliser pendant l'exécution.  
  
-   **OMP\_DYNAMIC** active ou désactive le réglage dynamique du nombre de threads.  
  
-   **OMP\_NESTED** active ou désactive le parallélisme imbriqué.  
  
 Les exemples dans ce chapitre affichent uniquement comment ces variables peuvent être définies dans des environnements de shell UNIX C \(csh\).  Dans le shell de Korn et les environnements DOS les actions sont semblables, comme suit :  
  
 csh :  
 setenv OMP\_SCHEDULE « dynamique »  
  
 ksh :  
 exportation OMP\_SCHEDULE\= " dynamique »  
  
 Arrière :  
 définissez OMP\_SCHEDULE\= " dynamique »