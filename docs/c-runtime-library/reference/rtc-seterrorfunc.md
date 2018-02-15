---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _RTC_SetErrorFunc
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
apitype: DLLExport
f1_keywords:
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
dev_langs:
- C++
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89d1ddf7b95b44c005d2e55f3813796fa21f716b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="rtcseterrorfunc"></a>_RTC_SetErrorFunc
Désigne une fonction comme gestionnaire pour signaler les vérifications d’erreurs au moment de l’exécution (RTC). Cette fonction est déconseillée. Utilisez `_RTC_SetErrorFuncW` à la place.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn function   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *function*  
 L’adresse de la fonction qui va gérer les vérifications d’erreurs au moment de l’exécution.  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction d’erreur définie précédemment. S’il n’existe pas de fonction définie précédemment, retourne NULL.  
  
## <a name="remarks"></a>Notes  
 N’utilisez pas cette fonction. Utilisez `_RTC_SetErrorFuncW`à la place. Elle est conservée uniquement pour assurer la compatibilité descendante.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérifications des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)