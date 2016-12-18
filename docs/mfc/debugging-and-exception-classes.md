---
title: "D&#233;bogage et classes d&#39;exceptions | Microsoft Docs"
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
  - "vc.classes.debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déboguer (MFC), classes de débogage"
  - "déboguer (MFC), classes d'exceptions"
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;bogage et classes d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes fournissent la prise en charge pour déboguer l'allocation dynamique de la mémoire et pour passer les informations d'exception depuis la fonction où l'exception est levée vers la fonction où elle est interceptée.  
  
 Utilisez les classes [CDumpContext](../mfc/reference/cdumpcontext-class.md) et [CMemoryState](../mfc/reference/cmemorystate-structure.md) lors du développement pour assister le débogage, comme décrit dans [Applications MFC de débogage](../Topic/MFC%20Debugging%20Techniques.md).  Utilisez [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) pour déterminer la classe d'un objet au moment de l'exécution, comme décrit dans l'article [Les informations sur la classe en cours d'accès](../mfc/accessing-run-time-class-information.md).  L'infrastructure utilise `CRuntimeClass` pour créer dynamiquement des objets d'une classe donnée.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)