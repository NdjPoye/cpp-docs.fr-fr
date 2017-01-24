---
title: "_get_timezone | Microsoft Docs"
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
  - "_get_timezone"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_get_timezone"
  - "get_timezone"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fuseaux horaires"
  - "get_timezone (fonction)"
  - "_get_timezone (fonction)"
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_timezone
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la différence en secondes entre le temps universel coordonné \(UTC\) et l'heure locale.  
  
## Syntaxe  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### Paramètres  
 `seconds`  
 La différence en secondes entre l'heure UTC et l'heure locale.  
  
## Valeur de retour  
 Zéro en cas de réussite ou une valeur `errno` si une erreur se produit.  
  
## Notes  
 La fonction `_get_timezone` récupère la différence en secondes entre UTC et l'heure locale en tant qu'entier.  La valeur par défaut est de 28.800 secondes, pour l'heure standard du Pacifique \(huit heures derrière UTC\).  
  
 Si `seconds` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_timezone`|\<time.h\>|  
  
 Pour plus d'informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)