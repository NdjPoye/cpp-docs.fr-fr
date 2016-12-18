---
title: "_CRTDBG_MAP_ALLOC | Microsoft Docs"
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
  - "CRTDBG_MAP_ALLOC"
  - "_CRTDBG_MAP_ALLOC"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRTDBG_MAP_ALLOC (macro)"
  - "allocation de mémoire, dans les builds en version debug"
  - "CRTDBG_MAP_ALLOC (macro)"
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CRTDBG_MAP_ALLOC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quend l'indicateur de **\_CRTDBG\_MAP\_ALLOC** est défini dans la version de débogage d'une application, la version de base des fonctions heap sont mappées directement à leur version de débogage.  L'indicateur est utilisé dans Crtdbg.h pour effectuer le mappage.  Cet indicateur est disponible uniquement lorsque l'indicateur [\_DEBUG](../c-runtime-library/debug.md) a été défini dans l'application.  
  
 Pour plus d'informations sur l'utilisation de la version de débogage par rapport à la version de base d'une fonction de segment de mémoire, consultez [Utilisation de la version de débogage par rapport à la version de base](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Voir aussi  
 [Indicateurs de contrôle](../c-runtime-library/control-flags.md)