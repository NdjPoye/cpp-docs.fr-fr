---
title: "_get_dstbias | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_dstbias"
  - "__dstbias"
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
  - "__dstbias"
  - "_get_dstbias"
  - "get_dstbias"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__dstbias"
  - "_get_dstbias (fonction)"
  - "décalage de l'heure d'été"
  - "get_dstbias (fonction)"
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_dstbias
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le décalage de l'heure d'été en secondes.  
  
## Syntaxe  
  
```  
  
error_t _get_dstbias(      int* seconds );  
```  
  
#### Paramètres  
 `seconds`  
 Décalage en secondes de l'heure d'été.  
  
## Valeur de retour  
 Zéro en cas de succès ou une valeur `errno` si une erreur se produit.  
  
## Notes  
 La fonction `_get_dstbias` récupère le nombre de secondes du passage à l'heure d'été sous forme d'entier.  Si l'heure d'été est en vigueur, le décalage par défaut est de 3 600 secondes, ce qui correspond au nombre de secondes dans une heure \(même si quelques régions observent un décalage de deux heures\).  
  
 Si `seconds` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `EINVAL` à `errno` et retourne `EINVAL`.  
  
 Nous vous recommandons d'utiliser cette fonction au lieu de la macro `_dstbias` ou de la fonction déconseillée `__dstbias`.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_dstbias`|\<time.h\>|  
  
 Pour plus d'informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)