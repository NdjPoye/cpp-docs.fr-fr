---
title: "Mappage des constantes et des variables globales | Microsoft Docs"
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
  - "_tenviron"
  - "_TEOF"
  - "_tfinddata_t"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tenviron (fonction)"
  - "_TEOF (type)"
  - "_tfinddata_t (fonction)"
  - "mappages de texte générique"
  - "tenviron (fonction)"
  - "TEOF (type)"
  - "tfinddata_t (fonction)"
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Mappage des constantes et des variables globales
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces constante de texte générique, variables globale, et mappings de types standard sont définis dans TCHAR.H et varient selon que la constante `_UNICODE` ou `_MBCS` a été défini dans votre programme.  
  
### Constante de texte générique et mappings de variables globales.  
  
|Texte générique \- nom de l'objet|SBCS \(\_UNICODE, \_MBCS pas définit\)|\_MBCS défini|\_UNICODE défini|  
|---------------------------------------|--------------------------------------------|-------------------|----------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## Voir aussi  
 [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md)   
 [Mappages de types de données](../c-runtime-library/data-type-mappings.md)   
 [Mappages de routine](../c-runtime-library/routine-mappings.md)   
 [Programme de texte générique, exemple](../c-runtime-library/a-sample-generic-text-program.md)   
 [Utilisation des mappages de texte générique](../c-runtime-library/using-generic-text-mappings.md)