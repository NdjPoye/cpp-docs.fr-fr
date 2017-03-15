---
title: "_(CRT)_DISABLE_PERFCRIT_LOCKS | Microsoft Docs"
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
  - "_CRT_DISABLE_PERFCRIT_LOCKS"
  - "CRT_DISABLE_PERFCRIT_LOCKS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_DISABLE_PERFCRIT_LOCKS (constante)"
  - "CRT_DISABLE_PERFCRIT_LOCKS (constante)"
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _(CRT)_DISABLE_PERFCRIT_LOCKS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désactive le verrouillage critique de performance dans les opérations d'E\/S.  
  
## Syntaxe  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## Notes  
 Ce symbole peut améliorer les performances dans les programmes axés sur les E\/S monothread en forçant les opérations d'E\/S à se limiter à un modèle monothread d'E\/S.  Pour plus d'informations, consultez [Performances des bibliothèques multithread](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)