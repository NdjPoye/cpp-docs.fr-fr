---
title: "_locking, constantes | Microsoft Docs"
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
  - "_LK_RLCK"
  - "_LK_NBLCK"
  - "_LK_LOCK"
  - "_LK_NBRLCK"
  - "_LK_UNLCK"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_LK_LOCK (constante)"
  - "_LK_NBLCK (constante)"
  - "_LK_NBRLCK (constante)"
  - "_LK_RLCK (constante)"
  - "_LK_UNLCK (constante)"
  - "LK_LOCK (constante)"
  - "LK_NBLCK (constante)"
  - "LK_NBRLCK (constante)"
  - "LK_RLCK (constante)"
  - "LK_UNLCK (constante)"
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _locking, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## Notes  
 L'argument *de mode* dans l'appel à la fonction `_locking` spécifie l'action de verrouillage à exécuter.  
  
 L'argument *de mode* doit être l'une des constantes manifestes suivantes.  
  
 `_LK_LOCK`  
 Verrouille les octets spécifiés.  Si les octets ne peuvent pas être verrouillés, tente de nouveau après 1 secondes.  Si, à l'issue de 10 tentatives, les octets ne peuvent pas être verrouillés, la fonction retourne une erreur.  
  
 `_LK_RLCK`  
 Identique à `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Verrouille les octets spécifiés.  Si les octets ne peuvent pas être verrouillés, la fonction retourne une erreur.  
  
 `_LK_NBRLCK`  
 Identique à `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Verrouille les octets spécifiés. \(Les octets doivent avoir été verrouillés.\)  
  
## Voir aussi  
 [\_locking](../c-runtime-library/reference/locking.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)