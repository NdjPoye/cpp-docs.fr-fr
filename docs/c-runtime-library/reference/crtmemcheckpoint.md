---
title: "_CrtMemCheckpoint | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemCheckpoint"
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
  - "CrtMemCheckpoint"
  - "_CrtMemCheckpoint"
  - "crtdbg/_CrtMemCheckpoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtMemCheckpoint (fonction)"
  - "_CrtMemCheckpoint (fonction)"
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtMemCheckpoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient l'état actuel du tas de débogage et le stocke dans une structure `_CrtMemState` fournie par l'application \(version debug uniquement\).  
  
## Syntaxe  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### Paramètres  
 `state`  
 Pointeur vers la structure `_CrtMemState` à remplir avec le point de contrôle de mémoire.  
  
## Notes  
 La fonction `_CrtMemCheckpoint` crée un instantané de l'état actuel du tas de débogage à tout moment donné. Cet instantané peut être utilisé par d’autres fonctions d’état du tas, comme [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md), pour aider à détecter les fuites de mémoire et d’autres problèmes. Quand [\_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemState` sont supprimés lors du prétraitement.  
  
 L'application doit passer un pointeur vers une instance précédemment allouée de la structure `_CrtMemState`, définie dans Crtdbg.h, dans le paramètre `state`. Si `_CrtMemCheckpoint` rencontre une erreur pendant la création du point de contrôle, la fonction génère un rapport de débogage `_CRT_WARN` qui décrit le problème.  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Si `state` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) est défini sur `EINVAL` et la fonction se termine.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h\>, \<errno.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions Debug de la bibliothèque UCRT.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)