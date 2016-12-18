---
title: "_get_tzname | Microsoft Docs"
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
  - "_get_tzname"
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
  - "_get_tzname"
  - "get_tzname"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_tzname (fonction)"
  - "get_tzname (fonction)"
  - "fuseaux horaires"
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_tzname
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère la représentation de chaîne de caractères du nom du fuseau horaire ou le nom de fuseau horaire standard de l'heure d'été \(DST\).  
  
## Syntaxe  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### Paramètres  
 \[out\] `pReturnValue`  
 La longueur de chaîne de`timeZoneName` inclue un marqueur de fin NULL.  
  
 \[out\] `timeZoneName`  
 L'adresse d'une chaîne de caractères pour la représentation du fuseau horaire oudu duseau horaire standard heure d'été \(DST\), dépend de `index`.  
  
 \[in\] `sizeInBytes`  
 La taille du caractère `timeZoneName` en octets.  
  
 \[in\] `index`  
 L'index de l'un des deux noms de fuseau horaire à récupérer.  
  
## Valeur de retour  
 Zéro en cas de réussite, sinon une valeur de type `errno`.  
  
 Si soit `timeZoneName` est `NULL`, soit `sizeInBytes` est nul ou négatif \(mais pas les deux\), un gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
### Conditions d'erreur  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Valeur de retour|Contenu de `timeZoneName`.|  
|--------------------|--------------------|-------------------|-------------|----------------------|--------------------------------|  
|taille du nom TZ|`NULL`|0|0 ou 1 ;|0|non modifié|  
|taille du nom TZ|any|\> 0|0 ou 1 ;|0|nom TZ|  
|non modifié|`NULL`|\> 0|any|`EINVAL`|non modifié|  
|non modifié|any|zéro|any|`EINVAL`|non modifié|  
|non modifié|any|\> 0|\> 1|`EINVAL`|non modifié|  
  
## Notes  
 La fonction `_get_tzname` récupère la représentation de chaîne de caractères du nom du fuseau horaire ou le nom de fuseau horaire standard d'heure d'été \(DST\) dans l'adresse de`timeZoneName` selon la valeur d'index, ainsi que la taille de la chaîne dans `pReturnValue`.  Si `timeZoneName` est `NULL` et que`sizeInBytes` est de zéro, la taille de la chaine de l'un des deux fuseaux horaires est retourné dans `pReturnValue`.  Les valeurs d'index doivent être 0 pour le fuseau horaire standard ou 1 pour le fuseau horaire standard d'heure d'été ; toutes les autres valeurs d'index ont des résultats indéterminés.  
  
### Valeurs d'index  
  
|`index`|Contenu de `timeZoneName`.|Valeur par défaut `timeZoneName`.|  
|-------------|--------------------------------|---------------------------------------|  
|0|Nom du fuseau horaire|"PST"|  
|1|Obtient le nom du fuseau horaire standard heure d'été.|"PDT"|  
|\> 1 ou \< 0|Affectez à `errno` la valeur `EINVAL`.|non modifié|  
  
 À moins que les valeurs ne soient explicitement modifiées au moment de l'exécution, les valeurs par défaut sont « PST » et « PDT » respectivement.  Les tailles de ces tableaux de caractères sont régies par valeur de`TZNAME_MAX`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h\>|  
  
 Pour plus d'informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [\_get\_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME\_MAX](../../c-runtime-library/tzname-max.md)