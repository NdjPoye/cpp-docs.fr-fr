---
title: "Partage de constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SH_DENYNO"
  - "_SH_DENYRD"
  - "_SH_DENYRW"
  - "_SH_DENYWR"
  - "_SH_COMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SH_COMPAT (constante)"
  - "_SH_DENYNO (constante)"
  - "_SH_DENYRD (constante)"
  - "_SH_DENYRW (constante)"
  - "_SH_DENYWR (constante)"
  - "SH_COMPAT (constante)"
  - "SH_DENYNO (constante)"
  - "SH_DENYRD (constante)"
  - "SH_DENYRW (constante)"
  - "SH_DENYWR (constante)"
  - "partage de constantes"
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Partage de constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constantes pour les modes de partage de fichiers.  
  
## Syntaxe  
  
```  
  
#include <share.h>  
  
```  
  
## Notes  
 L'argument *de shflag* détermine le mode de partage, composé d'une ou plusieurs constantes manifestes.  Ils peuvent être combinés avec les arguments *d'oflag* \(voir [Constantes de fichier](../c-runtime-library/file-constants.md)\).  
  
 Le tableau suivant répertorie les constantes et leurs significations :  
  
|Constante|Signification|  
|---------------|-------------------|  
|`_SH_DENYRW`|Refuse l'accès en lecture et en écriture au fichier.|  
|`_SH_DENYWR`|Refuse l'accès en écriture au fichier.|  
|`_SH_DENYRD`|Refuse l'accès en lecture au fichier.|  
|`_SH_DENYNO`|Accorde l'accès en lecture et en écriture|  
|`_SH_SECURE`|Définit le mode sécurisé \(lecture partagée, accès en écriture exclusif\).|  
  
## Voir aussi  
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)