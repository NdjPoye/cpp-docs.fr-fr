---
title: "_get_pgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_pgmptr"
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
  - "get_pgmptr"
  - "_get_pgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_get_pgmptr (fonction)"
  - "_pgmptr (variable globale)"
  - "get_pgmptr (fonction)"
  - "pgmptr (variable globale)"
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _get_pgmptr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la valeur actuelle de la variable globale `_pgmptr`.  
  
## Syntaxe  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### Paramètres  
 \[out\] `pValue`  
 Un pointeur vers une chaîne à remplir de valeur actuelle de la variable `_pgmptr`.  
  
## Valeur de retour  
 Retourne zéro si l'opération a réussi ; un code d'erreur en cas de échec.  Si`pValue`est `NULL`, tle gestionnaire de paramètres invalide est appelé comme décrit dans[Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
## Notes  
 La variable globale `_pgmptr`contient le chemin d'accès complet au fichier exécutable associé au processus.  Pour plus d'informations, consultez [\_pgmptr, \_wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_get\_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)