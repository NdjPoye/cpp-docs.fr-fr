---
title: "_CrtMemDumpAllObjectsSince | Microsoft Docs"
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
  - "_CrtMemDumpAllObjectsSince"
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
  - "CrtMemDumpAllObjectsSince"
  - "_CrtMemDumpAllObjectsSince"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtMemDumpAllObjectsSince (fonction)"
  - "CrtMemDumpAllObjectsSince (fonction)"
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemDumpAllObjectsSince
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Elimine des informations sur les objets du tas depuis le début de l'exécution du programme ou d'un état du tas spécifié \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### Paramètres  
 `state`  
 Pointeur vers l'état du tas à partir duquel démarrer l'élimination ou **NULL**.  
  
## Notes  
 La fonction `_CrtMemDumpAllObjectsSince` fait un dump des informations d'en\-tête du débogage d'objets alloués dans le tas dans un formulaire par lisible.  Les informations de dump peuvent être utilisées par l'application pour effectuer un suivi des allocations et détecter les problèmes de mémoire.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtMemDumpAllObjectsSince` sont supprimés pendant le prétraitement.  
  
 `_CrtMemDumpAllObjectsSince` utilise la valeur du paramètre `state` pour déterminer où démarrer l'opération de dump.  Pour démarrer l'élimination à partir d'un état du tas spécifié, le paramètre `state` doit être un pointeur vers une structure **\_CrtMemState** qui a été effectuée par [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) avant l'appel de `_CrtMemDumpAllObjectsSince`.  Lorsque `state` est **NULL**, la fonction commence le dump dès le début de l'exécution du programme.  
  
 Si l'application a installé une fonction de raccordement de dump en appelant [\_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md), chaque fois que `_CrtMemDumpAllObjectsSince` fait un dump des informations sur un type de bloc `_CLIENT_BLOCK` elle appelle la fonction fournie par l'application de dump également.  Par défaut, les blocs internes du runtime C \(`_CRT_BLOCK`\) ne sont pas inclus dans les opérations d'image mémoire.  La fonction [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour mettre à 1 le bit de `_CRTDBG_CHECK_CRT_DF` **\_crtDbgFlag** pour inclure ces blocs.  En outre, les blocs marqués comme libérés ou ignorés \(**\_FREE\_BLOCK**, **\_IGNORE\_BLOCK**\) ne sont pas inclus dans l'image mémoire.  
  
 Pour plus d'informations sur les fonctions d'état du tas et la structure de `_CrtMemState`, consultez [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Pour plus d'informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**\_CrtMemDumpAll\-ObjectsSince**|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour un exemple d'utilisation de `_CrtMemDumpAllObjectsSince`, consultez [crt\_dbg2](http://msdn.microsoft.com/fr-fr/21e1346a-6a17-4f57-b275-c76813089167).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)