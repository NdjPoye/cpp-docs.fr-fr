---
title: "_CrtDoForAllClientObjects | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDoForAllClientObjects"
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
  - "_CrtDoForAllClientObjects"
  - "CrtDoForAllClientObjects"
  - "crtdbg/_CrdDoForAllClientObjects"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtDoForAllClientObjects (fonction)"
  - "CrtDoForAllClientObjects (fonction)"
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDoForAllClientObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle une fonction fournie par l'application pour tous les types `_CLIENT_BLOCK` du tas \(version de débogage uniquement\).  
  
## Syntaxe  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### Paramètres  
 `pfn`  
 Pointeur vers la fonction de rappel de la fonction fournie par l'application. Le premier paramètre de cette fonction pointe vers les données. Le second paramètre est le pointeur de contexte qui est passé à l'appel à `_CrtDoForAllClientObjects`.  
  
 `context`  
 Pointeur vers le contexte fourni par l'application à passer à la fonction fournie par l'application.  
  
## Notes  
 La fonction `_CrtDoForAllClientObjects` recherche dans la liste liée du tas des blocs de mémoire avec le type `_CLIENT_BLOCK` et appelle la fonction fournie par l'application quand un bloc de ce type est trouvé. Le bloc trouvé et le paramètre `context` sont passés comme arguments à la fonction fournie par l'application. Pendant le débogage, une application peut effectuer le suivi d'un groupe spécifique d'allocations en appelant de façon explicite les fonctions du tas de débogage pour allouer la mémoire et en indiquant que le type de bloc `_CLIENT_BLOCK` doit être affecté aux blocs. Il est alors possible d'assurer le suivi de ces blocs séparément ainsi que de créer des rapports correspondants différents pendant la création de rapports sur la détection des fuites et l'état de la mémoire.  
  
 Si le champ de bits `_CRTDBG_ALLOC_MEM_DF` de l’indicateur [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) n’est pas activé, `_CrtDoForAllClientObjects` se termine immédiatement. Quand [\_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtDoForAllClientObjects` sont supprimés lors du prétraitement.  
  
 Pour plus d’informations sur le type `_CLIENT_BLOCK` et la façon dont il peut être utilisé par d’autres fonctions de débogage, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Si `pfn` a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) est défini sur `EINVAL` et la fonction se termine.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h\>, \<errno.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des bibliothèques Runtime C.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions)   
 [\_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)