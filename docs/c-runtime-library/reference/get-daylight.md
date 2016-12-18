---
title: "_get_daylight | Microsoft Docs"
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
  - "__daylight"
  - "_get_daylight"
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
  - "get_daylight"
  - "_get_daylight"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_daylight (fonction)"
  - "décalage de l'heure d'été"
  - "get_daylight (fonction)"
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_daylight
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le décalage de l'heure d'été en heures.  
  
## Syntaxe  
  
```  
  
error_t _get_daylight(      int* hours );  
```  
  
#### Paramètres  
 `hours`  
 Décalage en heures de l'heure d'été.  
  
## Valeur de retour  
 Zéro en cas de succès ou une valeur `errno` si une erreur se produit.  
  
## Notes  
 La fonction `_get_daylight` récupère le nombre d'heures du passage à l'heure d'été sous forme d'entier.  Si l'heure d'été est en vigueur, le décalage par défaut est d'une heure \(même si quelques régions observent un décalage de deux heures\).  
  
 Si `hours` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `EINVAL` à `errno` et retourne `EINVAL`.  
  
 Nous vous recommandons d'utiliser cette fonction au lieu de la macro `_daylight` ou de la fonction déconseillée `__daylight`.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_daylight`|\<time.h\>|  
  
 Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../../c-runtime-library/reference/get-tzname.md)