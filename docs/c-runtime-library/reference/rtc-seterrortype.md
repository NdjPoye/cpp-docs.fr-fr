---
title: _RTC_SetErrorType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 78f056e65523a39477bf138e6bd1664e0945a899
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="rtcseterrortype"></a>_RTC_SetErrorType
Associe une erreur qui est détectée par les vérifications d’erreurs au moment de l’exécution (RTC) avec un type. Votre gestionnaire d’erreurs traite la sortie des erreurs du type spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _RTC_SetErrorType(  
   _RTC_ErrorNumber errnum,  
   int ErrType   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *errnum*  
 Un nombre entre zéro et un de moins que la valeur retournée par [_RTC_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md).  
  
 *ErrType*  
 Valeur à affecter à ce *errnum*. Par exemple, vous pouvez utiliser une virgule **_CRT_ERROR**. Si vous utilisez `_CrtDbgReport` comme gestionnaire d’erreurs, *ErrType* peut être seulement un des symboles définis dans [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md). Si vous disposez de votre propre gestionnaire d’erreurs ([_RTC_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)), vous pouvez avoir autant d’ *ErrType*qu’il y a d’ *errnum*.  
  
 Un *ErrType* _RTC_ERRTYPE_IGNORE a une signification spéciale pour `_CrtSetReportMode`; l’erreur est ignorée.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur précédente pour le type d’erreur `type`.  
  
## <a name="remarks"></a>Notes  
 Par défaut, toutes les erreurs sont définies sur *ErrType* = 1, qui correspond à **_CRT_ERROR**. Pour plus d’informations sur les types d’erreurs par défaut comme **_CRT_ERROR**, consultez [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Consultez [Utilisation de contrôles d’exécution sans la bibliothèque Runtime C](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [_RTC_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Vérification des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)
