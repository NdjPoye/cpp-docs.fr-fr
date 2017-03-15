---
title: _get_dstbias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
dev_langs:
- C++
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 336f03207c1ead18dd7e47f44fd8c1055da4bc0e
ms.lasthandoff: 02/24/2017

---
# <a name="getdstbias"></a>_get_dstbias
Récupère le décalage de l'heure d'été en secondes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      error_t _get_dstbias(   
    int* seconds  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `seconds`  
 Décalage en secondes de l'heure d'été.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de succès ou une valeur `errno` si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `_get_dstbias` récupère le nombre de secondes du passage à l'heure d'été sous forme d'entier. Si l'heure d'été est en vigueur, le décalage par défaut est de 3 600 secondes, ce qui correspond au nombre de secondes dans une heure (même si quelques régions observent un décalage de deux heures).  
  
 Si `seconds` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
 Nous vous recommandons d'utiliser cette fonction au lieu de la macro `_dstbias` ou de la fonction déconseillée `__dstbias`.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_dstbias`|\<time.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_timezone](../../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
