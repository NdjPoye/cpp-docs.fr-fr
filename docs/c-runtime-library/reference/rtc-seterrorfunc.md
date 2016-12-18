---
title: "_RTC_SetErrorFunc | Microsoft Docs"
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
  - "_RTC_SetErrorFunc"
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
  - "RTC_SetErrorFunc"
  - "_RTC_SetErrorFunc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "RTC_SetErrorFunc (fonction)"
  - "_RTC_SetErrorFunc (fonction)"
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _RTC_SetErrorFunc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désigne une fonction comme gestionnaire pour signaler les vérifications d’erreurs au moment de l’exécution \(RTC\). Cette fonction est déconseillée. Utilisez `_RTC_SetErrorFuncW` à la place.  
  
## Syntaxe  
  
```  
  
_RTC_error_fn _RTC_SetErrorFunc(  
   _RTC_error_fn  
 function   
);  
  
```  
  
#### Paramètres  
 *function*  
 L’adresse de la fonction qui va gérer les vérifications d’erreurs au moment de l’exécution.  
  
## Valeur de retour  
 La fonction d’erreur définie précédemment. S’il n’existe pas de fonction définie précédemment, retourne NULL.  
  
## Notes  
 N’utilisez pas cette fonction. Utilisez `_RTC_SetErrorFuncW` à la place. Elle est conservée uniquement pour assurer la compatibilité descendante.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorFunc`|\<rtcapi.h\>|  
  
 Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_CrtDbgReport, \_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [Vérifications des erreurs au moment de l'exécution](../../c-runtime-library/run-time-error-checking.md)