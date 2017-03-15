---
title: "HUGE_VAL, _HUGE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_HUGE"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_HUGE"
  - "HUGE_VAL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HUGE (constante)"
  - "HUGE_VAL (constante)"
  - "valeur double"
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# HUGE_VAL, _HUGE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <math.h>  
  
```  
  
## Notes  
 `HUGE_VAL` est la plus grande valeur double représentable.  Cette valeur est retournée par de nombreuses fonctions mathématiques d'exécution lorsqu'une erreur se produit.  Pour certaines fonctions, –`HUGE_VAL` est retourné.  `HUGE_VAL` est défini comme `_HUGE`, mais fonctions mathématiques à l'exécution retournent `HUGE_VAL`.  Vous devez également utiliser `HUGE_VAL` dans votre code pour des raisons de cohérence.  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)