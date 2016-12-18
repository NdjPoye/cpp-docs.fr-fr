---
title: "_get_wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_wpgmptr"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_wpgmptr"
  - "_get_wpgmptr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_wpgmptr (fonction)"
  - "_wpgmptr (variable globale)"
  - "get_wpgmptr (fonction)"
  - "wpgmptr (variable globale)"
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_wpgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la valeur actuelle de la variable globale `_wpgmptr`.  
  
## Syntaxe  
  
```  
errno_t _get_wpgmptr(     wchar_t **pValue  );  
```  
  
#### Paramètres  
 \[out\] `pValue`  
 Pointeur vers une chaîne à remplir avec la valeur actuelle de la variable `_wpgmptr`.  
  
## Valeur de retour  
 Retourne zéro si l'opération a réussi et un code d'erreur en cas d'échec.  Si `pValue` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `EINVAL` à `errno` et retourne `EINVAL`.  
  
## Notes  
 La variable globale `_wpgmptr` contient le chemin d'accès complet du fichier exécutable associé au processus sous la forme d'une chaîne à caractères larges.  Pour plus d'informations, consultez [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_wpgmptr`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_get\_pgmptr](../../c-runtime-library/reference/get-pgmptr.md)