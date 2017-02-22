---
title: "_RTC_SetErrorType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_RTC_SetErrorType"
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
  - "RTC_SetErrorType"
  - "_RTC_SetErrorType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erreurs d'exécution"
  - "RTC_SetErrorType (fonction)"
  - "_RTC_SetErrorType (fonction)"
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _RTC_SetErrorType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Associe une erreur qui est détectée par les vérifications d’erreurs au moment de l’exécution \(RTC\) avec un type. Votre gestionnaire d’erreurs traite la sortie des erreurs du type spécifié.  
  
## Syntaxe  
  
```  
  
int _RTC_SetErrorType(  
   _RTC_ErrorNumber  
errnum  
,  
   int  
ErrType   
);  
  
```  
  
#### Paramètres  
 *errnum*  
 Un nombre entre zéro et un de moins que la valeur retournée par [\_RTC\_NumErrors](../../c-runtime-library/reference/rtc-numerrors.md).  
  
 *ErrType*  
 Valeur à affecter à ce *errnum*. Par exemple, vous pouvez utiliser une virgule **\_CRT\_ERROR**. Si vous utilisez `_CrtDbgReport` comme gestionnaire d’erreurs, *ErrType* peut être seulement un des symboles définis dans [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md). Si vous disposez de votre propre gestionnaire d’erreurs \([\_RTC\_SetErrorFunc](../../c-runtime-library/reference/rtc-seterrorfunc.md)\), vous pouvez avoir autant d’*ErrType* qu’il y a d’*errnum*.  
  
 Un *ErrType* \_RTC\_ERRTYPE\_IGNORE a une signification spéciale pour `_CrtSetReportMode` ; l’erreur est ignorée.  
  
## Valeur de retour  
 La valeur précédente pour le type d’erreur `type`.  
  
## Notes  
 Par défaut, toutes les erreurs sont définies sur *ErrType* \= 1, qui correspond à **\_CRT\_ERROR**. Pour plus d’informations sur les types d’erreurs par défaut comme **\_CRT\_ERROR**, consultez [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
 Avant d’appeler cette fonction, vous devez d’abord appeler une des fonctions d’initialisation de vérification d’erreurs au moment de l’exécution. Consultez [Utilisation des vérifications d’erreurs au moment de l’exécution sans la bibliothèque CRT](../Topic/Using%20Run-Time%20Checks%20Without%20the%20C%20Run-Time%20Library.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_RTC_SetErrorType`|\<rtcapi.h\>|  
  
 Pour plus d'informations, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_RTC\_GetErrDesc](../../c-runtime-library/reference/rtc-geterrdesc.md)   
 [Vérifications des erreurs au moment de l'exécution](../../c-runtime-library/run-time-error-checking.md)