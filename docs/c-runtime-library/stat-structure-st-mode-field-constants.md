---
title: "Constantes du champ st_mode de la structure _stat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "S_IFCHR"
  - "S_IFDIR"
  - "_S_IWRITE"
  - "S_IFMT"
  - "_S_IFDIR"
  - "_S_IREAD"
  - "S_IEXEC"
  - "_S_IEXEC"
  - "_S_IFMT"
  - "S_IWRITE"
  - "S_IFREG"
  - "S_IREAD"
  - "_S_IFCHR"
  - "_S_IFREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_S_IEXEC (constante)"
  - "_S_IFCHR (constante)"
  - "_S_IFDIR (constante)"
  - "_S_IFMT (constante)"
  - "_S_IFREG (constante)"
  - "_S_IREAD (constante)"
  - "_S_IWRITE (constante)"
  - "S_IEXEC (constante)"
  - "S_IFCHR (constante)"
  - "S_IFDIR (constante)"
  - "S_IFMT (constante)"
  - "S_IFREG (constante)"
  - "S_IREAD (constante)"
  - "S_IWRITE (constante)"
  - "st_mode field (constantes)"
  - "structure stat"
  - "structure stat, constantes"
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Constantes du champ st_mode de la structure _stat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## Notes  
 Ces constantes sont utilisées pour indiquer le type de fichier dans le champ de **st\_mode** de la[structure de \_stat](../c-runtime-library/standard-types.md).  
  
 Les constantes de masque de bits sont décrites ci\-dessous :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_S_IFMT`|Masque de type de fichier|  
|`_S_IFDIR`|Répertoire|  
|`_S_IFCHR`|Caractère spécial \(indique si un outil est pret\)|  
|`_S_IFREG`|Normale|  
|`_S_IREAD`|Autorisation de lecture, propriétaire|  
|`_S_IWRITE`|Autorisation d'écriture, propriétaire|  
|`_S_IEXEC`|Atorisation d'execution\/recherche, propriétaire|  
  
## Voir aussi  
 [\_stat, \_wstat, fonctions](../c-runtime-library/reference/stat-functions.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [Types standard](../c-runtime-library/standard-types.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)