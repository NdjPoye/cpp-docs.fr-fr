---
title: _get_timezone | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_timezone
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
- _get_timezone
- get_timezone
dev_langs:
- C++
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1810a9c79d21b6a0b19f5f4e4f2d4c59d286e5b7
ms.lasthandoff: 02/24/2017

---
# <a name="gettimezone"></a>_get_timezone
Récupère la différence en secondes entre le temps universel coordonné (UTC) et l’heure locale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      error_t _get_timezone(   
    long* seconds  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `seconds`  
 Différence en secondes entre l’heure UTC et l’heure locale.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro en cas de succès ou une valeur `errno` si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `_get_timezone` récupère la différence en secondes entre l’heure UTC et l’heure locale sous la forme d’un entier. La valeur par défaut est de 28 800 secondes, pour l’heure du Pacifique (huit heures après l’heure UTC).  
  
 Si `seconds` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_timezone`|\<time.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion du temps](../../c-runtime-library/time-management.md)   
 [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)   
 [_get_daylight](../../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../../c-runtime-library/reference/get-dstbias.md)   
 [_get_tzname](../../c-runtime-library/reference/get-tzname.md)
