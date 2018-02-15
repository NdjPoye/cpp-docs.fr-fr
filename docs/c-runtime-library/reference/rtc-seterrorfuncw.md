---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f586823ffcab1e8d602375c9d955c78ac64c043f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
Désigne une fonction comme gestionnaire pour signaler les vérifications d’erreurs au moment de l’exécution (RTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `function`  
 L’adresse de la fonction qui va gérer les vérifications d’erreurs au moment de l’exécution.  
  
## <a name="return-value"></a>Valeur de retour  
 Fonction d’erreur définie précédemment ou `NULL` en l’absence de fonction définie précédemment.  
  
## <a name="remarks"></a>Notes  
 Dans du nouveau code, utilisez seulement `_RTC_SetErrorFuncW`. `_RTC_SetErrorFunc` est inclus dans la bibliothèque seulement pour assurer la compatibilité descendante.  
  
 Le rappel `_RTC_SetErrorFuncW` s’applique uniquement au composant auquel il était lié, mais pas globalement.  
  
 Assurez-vous que l’adresse que vous passez à `_RTC_SetErrorFuncW` est celle d’une fonction de gestion des erreurs valide.  
  
 Si une erreur a été affectée un type de -1 à l’aide de [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), la fonction de gestion d’erreur n’est pas appelée.  
  
 Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Pour plus d'informations, consultez [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
 **_RTC_error_fnW** est défini comme suit :  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  *linenumber* **, const wchar_t \*** `moduleName` **, const wchar_t \*** *format* **, ...);**  
  
 où :  
  
 `errorType`  
 Le type d’erreur qui est spécifié par [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md).  
  
 *filename*  
 Le fichier source où la défaillance s’est produite, ou null si aucune information de débogage n’est disponible.  
  
 *linenumber*  
 La ligne de *filename* où la défaillance s’est produite, ou 0 si aucune information de débogage n’est disponible.  
  
 `moduleName`  
 Le fichier DLL ou le nom du fichier exécutable où la défaillance s’est produite.  
  
 *format*  
 chaîne de style printf pour afficher un message d’erreur, en utilisant les paramètres restants. Le premier argument de VA_ARGLIST est le numéro de l’erreur RTC qui s’est produite.  
  
 Pour obtenir un exemple qui montre comment utiliser **_RTC_error_fnW**, consultez [Personnalisation des contrôles natifs à l’exécution](/visualstudio/debugger/native-run-time-checks-customization).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérifications des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)