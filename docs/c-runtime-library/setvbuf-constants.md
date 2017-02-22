---
title: "setvbuf, constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_IOFBF"
  - "_IONBF"
  - "_IOLBF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_IOFBF (constante)"
  - "_IOLBF (constante)"
  - "_IONBF (constante)"
  - "IOFBF (constante)"
  - "IOLBF (constante)"
  - "IONBF (constante)"
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# setvbuf, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <stdio.h>  
  
```  
  
## Notes  
 Ces constantes représentent le type de mémoire tampon pour `setvbuf`.  
  
 Les valeurs possibles sont fournies par les constantes manifestes suivantes :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_IOFBF`|Mise en mémoire tampon saturée : La mémoire tampon spécifiée dans l'appel à `setvbuf` est utilisée et sa taille est spécifiée dans l'appel à `setvbuf`.  Si le pointeur de mémoire tampon est **NULL**, la mémoire tampon allouée automatiquement à la taille spécifiée est utilisée.|  
|`_IOLBF`|Identique à `_IOFBF`.|  
|`_IONBF`|Aucune mémoire tampon est utilisée, indépendamment des arguments dans l'appel à `setvbuf`.|  
  
## Voir aussi  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)