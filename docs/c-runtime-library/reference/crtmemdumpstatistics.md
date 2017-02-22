---
title: "_CrtMemDumpStatistics | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemDumpStatistics"
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
  - "CrtMemDumpStatistics"
  - "_CrtMemDumpStatistics"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtMemDumpStatistics (fonction)"
  - "CrtMemDumpStatistics (fonction)"
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _CrtMemDumpStatistics
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vide les informations d’en\-tête de débogage pour l’état du tas spécifié sous une forme lisible par l’utilisateur \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### Paramètres  
 `state`  
 Pointeur vers l’état du tas à vider.  
  
## Notes  
 La fonction `_CrtMemDumpStatistics` vide les informations d’en\-tête de débogage pour l’état du tas spécifié sous une forme lisible par l’utilisateur. Les statistiques de vidage permettent à l’application d’effectuer le suivi des allocations, et de détecter les problèmes de mémoire. L’état de la mémoire peut contenir un état de tas spécifique, ou la différence entre deux états. Quand [\_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemDumpStatistics` sont supprimés durant le prétraitement.  
  
 Le paramètre `state` doit être un pointeur vers une structure `_CrtMemState` remplie par [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) ou retournée par [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) avant l’appel de `_CrtMemDumpStatistics`. Si `state` a la valeur `NULL`, le gestionnaire de paramètres non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et aucune action n’est retournée. Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur les fonctions d’état du tas et la structure `_CrtMemState`, consultez [Heap State Reporting Functions](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h\>|\<errno.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions Debug de [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)