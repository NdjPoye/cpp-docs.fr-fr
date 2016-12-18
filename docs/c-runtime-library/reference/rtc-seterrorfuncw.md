---
title: "_RTC_SetErrorFuncW | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_SetErrorFuncW"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_RTC_SetErrorFuncW"
  - "RTC_SetErrorFuncW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "erreurs d'exécution"
  - "RTC_SetErrorFuncW (fonction)"
  - "_RTC_error_fnW (typedef)"
  - "_RTC_SetErrorFuncW (fonction)"
  - "RTC_error_fnW (typedef)"
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorFuncW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désigne une fonction comme gestionnaire pour signaler les vérifications d’erreurs au moment de l’exécution \(RTC\).  
  
## Syntaxe  
  
```  
  
_RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW  
 function   
);  
  
```  
  
#### Paramètres  
 `function`  
 L’adresse de la fonction qui va gérer les vérifications d’erreurs au moment de l’exécution.  
  
## Valeur de retour  
 La fonction d’erreur définie précédemment, ou `NULL` s’il n’existe pas de fonction définie précédemment.  
  
## Notes  
 Dans du nouveau code, utilisez seulement `_RTC_SetErrorFuncW`.`_RTC_SetErrorFunc` est inclus dans la bibliothèque seulement pour assurer la compatibilité descendante.  
  
 Le rappel `_RTC_SetErrorFuncW` s’applique uniquement au composant auquel il était lié, mais pas globalement.  
  
 Assurez\-vous que l’adresse que vous passez à `_RTC_SetErrorFuncW` est celle d’une fonction de gestion des erreurs valide.  
  
 Si un type \-1 a été affecté à une erreur à l’aide de [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md), la fonction de gestion des erreurs n’est pas appelée.  
  
 Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Pour plus d'informations, consultez [Utilisation des vérifications à l'exécution sans la bibliothèque Runtime C](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md).  
  
 **\_RTC\_error\_fnW** est définie comme suit :  
  
 **typedef int \(\_\_cdecl \*\_RTC\_error\_fnW\)\(int**  `errorType` **, const wchar\_t \*** *filename* **, int**  *linenumber* **, const wchar\_t \*** `moduleName` **, const wchar\_t \*** *format* **, ...\);**  
  
 où :  
  
 `errorType`  
 Le type d’erreur qui est spécifié par [\_RTC\_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md).  
  
 *filename*  
 Le fichier source où la défaillance s’est produite, ou null si aucune information de débogage n’est disponible.  
  
 *linenumber*  
 La ligne de *filename* où la défaillance s’est produite, ou 0 si aucune information de débogage n’est disponible.  
  
 `moduleName`  
 Le fichier DLL ou le nom du fichier exécutable où la défaillance s’est produite.  
  
 *format*  
 chaîne de style printf pour afficher un message d’erreur, en utilisant les paramètres restants. Le premier argument de VA\_ARGLIST est le numéro de l’erreur RTC qui s’est produite.  
  
 Pour obtenir un exemple qui montre comment utiliser **\_RTC\_error\_fnW**, consultez [Personnalisation des contrôles natifs à l'exécution](../Topic/Native%20Run-Time%20Checks%20Customization.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h\>|  
  
 Pour plus d'informations, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérifications des erreurs au moment de l'exécution](../../c-runtime-library/run-time-error-checking.md)