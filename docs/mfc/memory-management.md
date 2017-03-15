---
title: "Gestion de la m&#233;moire | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "mémoire"
  - "allocation de mémoire"
  - "allocation de mémoire, MFC"
  - "mémoire, gérer"
  - "MFC, gestion de la mémoire"
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion de la m&#233;moire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce groupe d'articles explique comment tirer parti des services à caractère général de bibliothèque MFC \(MFC\) relatifs à la gestion de la mémoire.  L'allocation de mémoire peut être divisée en deux catégories : allocation et allocations des segments du cadre.  
  
 La principale différence entre les deux techniques d'allocation est celle de l'allocation de cadre que vous utilisez généralement par le bloc de mémoire en lui\-même, alors qu'avec l'allocation des segments vous êtes toujours donné pointeur vers le bloc de mémoire.  Une différence majeure entre les deux modèles est que les cadres objets sont automatiquement supprimés, tandis que les objets heap doivent être explicitement supprimé par le programmeur.  
  
 Pour plus d'informations non\-MFC sur la gestion de la mémoire dans les programmes pour windows, consultez le [Gestion de la mémoire](http://msdn.microsoft.com/library/windows/desktop/aa366779) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [allocation de cadre](../mfc/memory-management-frame-allocation.md)  
  
-   [allocation des tas](../mfc/memory-management-heap-allocation.md)  
  
-   [Allouer de la mémoire à un tableau](../mfc/memory-management-examples.md)  
  
-   [Libération de la mémoire à un tableau de segment](../mfc/memory-management-examples.md)  
  
-   [Allouer de la mémoire pour une structure de données](../mfc/memory-management-examples.md)  
  
-   [Allouer de la mémoire pour un objet](../mfc/memory-management-examples.md)  
  
-   [Blocs de mémoire fiable](../mfc/memory-management-resizable-memory-blocks.md)  
  
## Voir aussi  
 [Concepts](../mfc/mfc-concepts.md)   
 [Rubriques MFC générales](../mfc/general-mfc-topics.md)