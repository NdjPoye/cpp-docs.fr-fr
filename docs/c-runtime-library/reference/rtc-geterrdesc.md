---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: 12
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
ms.openlocfilehash: 4850b9e6da16ad2b446b532281d65cd3bf535698
ms.lasthandoff: 02/24/2017

---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc
Retourne une brève description d’un type de vérification d’erreurs au moment de l’exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      const char * _RTC_GetErrDesc(  
   _RTC_ErrorNumber errnum   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *errnum*  
 Un nombre entre zéro et un de moins que la valeur retournée par `_RTC_NumErrors`.  
  
## <a name="return-value"></a>Valeur de retour  
 Une chaîne de caractères qui contient une brève description d’un des types d’erreurs détectées par le système de vérification d’erreurs au moment de l’exécution. Si l’erreur est inférieure à zéro ou supérieure ou égale à la valeur retournée par [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md), `_RTC_GetErrDesc` retourne NULL.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_GetErrDesc`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [Vérification des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)