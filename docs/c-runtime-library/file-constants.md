---
title: "Constantes de fichier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_O_EXCL"
  - "_O_RDWR"
  - "_O_APPEND"
  - "_O_RDONLY"
  - "_O_TRUNC"
  - "_O_CREAT"
  - "_O_WRONLY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_O_APPEND (constante)"
  - "_O_CREAT (constante)"
  - "_O_EXCL (constante)"
  - "_O_RDONLY (constante)"
  - "_O_RDWR (constante)"
  - "_O_TRUNC (constante)"
  - "_O_WRONLY (constante)"
  - "O_APPEND (constante)"
  - "O_CREAT (constante)"
  - "O_EXCL (constante)"
  - "O_RDONLY (constante)"
  - "O_RDWR (constante)"
  - "O_TRUNC (constante)"
  - "O_WRONLY (constante)"
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Constantes de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Notes  
 L'expression entière formée à partir d'une ou plusieurs de ces constantes détermine le type d'opérations de lecture ou d'écriture autorisé.  Elle est formée d'en combinant un ou plusieurs constantes avec une constante à mode de traduction.  
  
 Les constantes de fichier sont les suivantes :  
  
 `_O_APPEND`  
 Replace le pointeur de fichier à la fin de le fichier avant chaque opération d'écriture.  
  
 `_O_CREAT`  
 Crée et ouvre un nouveau fichier pour une écriture ; cela n'a aucun effet si le fichier spécifié par *le nom de fichier* existe.  
  
 `_O_EXCL`  
 Retourne une valeur d'erreur si le fichier spécifié par *le nom de fichier* existe.  S'applique uniquement lorsqu'ils sont utilisés avec `_O_CREAT`.  
  
 `_O_RDONLY`  
 Ouvre le fichier en lecture seule ; si cette valeur est fournie, ni `_O_RDWR` ni `_O_WRONLY` ne peuvent être fournies.  
  
 `_O_RDWR`  
 Ouvre le fichier pour la lecture et l'écriture ; si cette valeur est fournie, ni `_O_RDONLY` ni `_O_WRONLY` ne peuvent être fournies.  
  
 `_O_TRUNC`  
 Ouvre et tronque un fichier existant à la longueur nulle ; le fichier doit avoir l'autorisation d'écriture.  Le contenu du fichier est détruit.  Si cet indicateur est fourni, vous ne pouvez pas spécifier `_O_RDONLY`.  
  
 `_O_WRONLY`  
 Ouvre le fichier en lecture seule ; si cette valeur est fournie, ni `_O_RDONLY` ni `_O_RDWR` ne peuvent être fournies.  
  
## Voir aussi  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)