---
title: _RTC_GetErrDesc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _RTC_GetErrDesc
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
dev_langs: C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 792407af9497148bea95333ee18028e0f8c953e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>Voir aussi  
 [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md)   
 [Vérification des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)