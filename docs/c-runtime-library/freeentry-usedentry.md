---
title: "_FREEENTRY, _USEDENTRY | Microsoft Docs"
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
  - "USEDENTRY"
  - "_USEDENTRY"
  - "_FREEENTRY"
  - "FREEENTRY"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_FREEENTRY (constante)"
  - "_USEDENTRY (constante)"
  - "FREEENTRY (constante)"
  - "USEDENTRY (constante)"
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _FREEENTRY, _USEDENTRY
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
#include <malloc.h>  
```  
  
## Notes  
 Ces constantes représentent les valeurs affectées par les routines `_heapwalk` à l'élément **\_useflag** de structure **\_HEAPINFO**.  Ils indiquent l'état de l'entrée du ségment de mémoire.  
  
## Voir aussi  
 [\_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)