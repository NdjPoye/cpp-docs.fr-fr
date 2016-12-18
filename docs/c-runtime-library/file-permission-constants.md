---
title: "Constantes d&#39;autorisations de fichier | Microsoft Docs"
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
  - "_S_IWRITE"
  - "_S_IREAD"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_S_IREAD (constante)"
  - "_S_IWRITE (constante)"
  - "constantes (C++), attributs de fichiers"
  - "autorisations fichier (C++)"
  - "S_IREAD (constante)"
  - "S_IWRITE (constante)"
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes d&#39;autorisations de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## Notes  
 Une des valeurs constantes est requise lorsque `_O_CREAT` \(`_open`, `_sopen`\) est spécifié.  
  
 L'argument `pmode` spécifie les paramètres d'autorisation du fichier comme suit.  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_S_IREAD`|Lecture autorisée.|  
|`_S_IWRITE`|Écriture autorisée.|  
|`_S_IREAD`  &#124; `_S_IWRITE`|Lecture et écriture autorisées.|  
  
 Lorsqu'elle est utilisée en tant qu'argument `pmode` pour `_umask`, la constante manifeste définit le paramètre d'autorisation, comme suit.  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_S_IREAD`|Écrire non \- autorisée \(fichier est en lecture seule\)|  
|`_S_IWRITE`|Lecture non \- autorisée \(fichier est en écriture seule\)|  
|`_S_IREAD`  &#124; `_S_IWRITE`|Ni lecture ni écriture autorisée|  
  
## Voir aussi  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../c-runtime-library/reference/umask.md)   
 [Types standard](../c-runtime-library/standard-types.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)