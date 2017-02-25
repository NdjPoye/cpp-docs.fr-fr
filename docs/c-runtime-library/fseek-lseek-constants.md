---
title: "fseek, _lseek, constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEEK_END"
  - "SEEK_SET"
  - "SEEK_CUR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEEK_CUR (constante)"
  - "SEEK_END (constante)"
  - "SEEK_SET (constante)"
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# fseek, _lseek, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <stdio.h>  
  
```  
  
## Notes  
 L'argument *d'origine* spécifie la position initiale et peut être l'une des constantes manifestes suivantes :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`SEEK_END`|fin du fichier|  
|`SEEK_CUR`|Position actuelle du pointeur de fichier|  
|`SEEK_SET`|Début du fichier|  
  
## Voir aussi  
 [fseek, \_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [\_lseek, \_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)