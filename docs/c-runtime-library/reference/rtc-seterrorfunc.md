---
title: _RTC_SetErrorFunc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 3088b225c75a5ddcdc83d8343bd9640073189e37
ms.lasthandoff: 02/24/2017

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
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérification des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)
