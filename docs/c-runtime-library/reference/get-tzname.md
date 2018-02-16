---
title: _get_tzname | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_tzname
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a44accc317bf387fcdd3ab7879020b13fba6858
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="gettzname"></a>_get_tzname
Récupère la représentation sous forme de chaîne de caractères du nom du fuseau horaire standard ou du nom du fuseau horaire d’été (DST).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _get_tzname(  
    size_t* pReturnValue,  
    char* timeZoneName,  
    size_t sizeInBytes,  
    int index      
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pReturnValue`  
 Longueur de chaîne de `timeZoneName`, y compris une marque de fin NULL.  
  
 [out] `timeZoneName`  
 Adresse d’une chaîne de caractères pour la représentation du nom du fuseau horaire standard ou du nom du fuseau horaire d’été (DST), en fonction de `index`.  
  
 [in] `sizeInBytes`  
 Taille de la chaîne de caractères `timeZoneName` en octets.  
  
 [in] `index`  
 Index d’un des deux noms de fuseaux horaires à récupérer.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de réussite, sinon une valeur de type `errno`.  
  
 Si `timeZoneName` a la valeur `NULL` ou que `sizeInBytes` est inférieur ou égal à zéro (une seule des deux conditions satisfaite), un gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`pReturnValue`|`timeZoneName`|`sizeInBytes`|`index`|Valeur de retour|Contenu de `timeZoneName`|  
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|  
|Taille du nom du fuseau horaire|`NULL`|0|0 ou 1|0|non modifié|  
|Taille du nom du fuseau horaire|any|> 0|0 ou 1|0|Nom du fuseau horaire|  
|non modifié|`NULL`|> 0|any|`EINVAL`|non modifié|  
|non modifié|any|zéro|any|`EINVAL`|non modifié|  
|non modifié|any|> 0|> 1|`EINVAL`|non modifié|  
  
## <a name="remarks"></a>Notes  
 La fonction `_get_tzname` récupère la représentation sous forme de chaîne de caractères du nom du fuseau horaire standard ou du nom du fuseau horaire d’été (DST) dans l’adresse de `timeZoneName` suivant la valeur d’index, ainsi que la taille de la chaîne dans `pReturnValue`. Si `timeZoneName` a la valeur `NULL` et que `sizeInBytes` est égal à zéro, seule la taille de la chaîne d’un des fuseaux horaires en octets est retournée dans `pReturnValue`. La valeur d’index doit être 0 (fuseau horaire standard) ou 1 (fuseau horaire d’été) ; toute autre valeur d’index engendre des résultats indéterminés.  
  
### <a name="index-values"></a>Valeurs d’index  
  
|`index`|Contenu de `timeZoneName`|Valeur par défaut de `timeZoneName`|  
|-------------|--------------------------------|----------------------------------|  
|0|Nom du fuseau horaire|« PST »|  
|1|Nom du fuseau horaire d’hiver|« PDT »|  
|> 1 ou < 0|`errno` défini sur `EINVAL`|non modifié|  
  
 À moins que les valeurs soient explicitement modifiées pendant l’exécution, les valeurs par défaut sont respectivement « PST » et « PDT ».  Les tailles de ces tableaux de caractères sont régies par la valeur `TZNAME_MAX`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_tzname`|\<time.h>|  
  
 Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [TZNAME_MAX](../../c-runtime-library/tzname-max.md)