---
title: "_crtDbgFlag | Microsoft Docs"
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
  - "_crtDbgFlag"
  - "crtDbgFlag"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_crtDbgFlag (constante)"
  - "crtDbgFlag (constante)"
  - "tas de débogage, indicateurs de contrôle"
  - "tas de débogage, suivre la mémoire sur"
  - "activer l'indicateur de suivi de l'allocation de mémoire"
  - "allocation de mémoire, indicateur de suivi"
  - "mémoire, suivre sur le tas de débogage"
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _crtDbgFlag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'indicateur **\_crtDbgFlag** est constitué de cinq champs de bits qui contrôlent la façon dont les allocations de mémoire sur la version de débogage du tas sont suivies, vérifiées, signalées et vidées.  Les champs de bits de l'indicateur sont définis à l'aide de la fonction [\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md).  Cet indicateur et ses champs de bits sont déclarés dans Crtdbg.h.  Cet indicateur n'est disponible que quand l'indicateur [\_DEBUG](../c-runtime-library/debug.md) a été défini dans l'application.  
  
 Pour plus d'informations sur l'utilisation de cet indicateur avec d'autres fonctions de débogage, voir [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  
  
## Voir aussi  
 [Indicateurs de contrôle](../c-runtime-library/control-flags.md)