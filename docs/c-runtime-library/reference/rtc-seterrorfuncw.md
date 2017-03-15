---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 15
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
ms.openlocfilehash: d71962eca033e5d3994c82e666102f44c62e82be
ms.lasthandoff: 02/24/2017

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
 Dans du nouveau code, utilisez seulement `_RTC_SetErrorFuncW`. `_RTC_SetErrorFunc` n’est inclus dans la bibliothèque que pour assurer une compatibilité descendante.  
  
 Le rappel `_RTC_SetErrorFuncW` s’applique uniquement au composant auquel il était lié, mais pas globalement.  
  
 Vérifiez que l’adresse que vous transmettez à `_RTC_SetErrorFuncW` est celle d’une fonction de gestion des erreurs valide.  
  
 Si un type -1 a été affecté à une erreur à l’aide de [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), la fonction de gestion des erreurs n’est pas appelée.  
  
 Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Pour plus d’informations, consultez [Utilisation de contrôles à l’exécution sans la bibliothèque Runtime C](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).  
  
 **_RTC_error_fnW** est défini comme suit :  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  *linenumber* **, const wchar_t \*** `moduleName` **, const wchar_t \*** *format* **, ...);**  
  
 où :  
  
 `errorType`  
 Le type d’erreur qui est spécifié par [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md).  
  
 *filename*  
 Le fichier source où la défaillance s’est produite, ou null si aucune information de débogage n’est disponible.  
  
 *linenumber*  
 La ligne dans *filename* où la défaillance s’est produite ou 0 si aucune information de débogage n’est disponible.  
  
 `moduleName`  
 Le fichier DLL ou le nom du fichier exécutable où la défaillance s’est produite.  
  
 *format*  
 Chaîne de style printf pour afficher un message d’erreur, en utilisant les paramètres restants. Le premier argument de VA_ARGLIST est le numéro de l’erreur RTC qui s’est produite.  
  
 Pour obtenir un exemple qui montre comment utiliser **_RTC_error_fnW**, consultez [Personnalisation des contrôles natifs à l’exécution](/visualstudio/debugger/native-run-time-checks-customization).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 Pour plus d’informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérification des erreurs au moment de l’exécution](../../c-runtime-library/run-time-error-checking.md)
