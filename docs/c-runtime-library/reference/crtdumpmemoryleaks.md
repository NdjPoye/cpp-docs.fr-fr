---
title: "_CrtDumpMemoryLeaks | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDumpMemoryLeaks"
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
  - "CRTDBG_LEAK_CHECK_DF"
  - "CRTDBG_CHECK_CRT_DF"
  - "_CRTDBG_LEAK_CHECK_DF"
  - "CrtDumpMemoryLeaks"
  - "_CrtDumpMemoryLeaks"
  - "_CRTDBG_CHECK_CRT_DF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtDumpMemoryLeaks (fonction)"
  - "CRTDBG_LEAK_CHECK_DF (macro)"
  - "_CRTDBG_LEAK_CHECK_DF (macro)"
  - "_CrtDumpMemoryLeaks (fonction)"
  - "CRTDBG_CHECK_CRT_DF (macro)"
  - "_CRTDBG_CHECK_CRT_DF (macro)"
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _CrtDumpMemoryLeaks
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fait un dump tous les blocs de mémoire dans le tas de débogage lorsqu'une fuite de mémoire a eu lieu \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## Valeur de retour  
 `_CrtDumpMemoryLeaks` renvoie TRUE si une fuite de mémoire est trouvée.  Sinon, la fonction retourne FALSE.  
  
## Notes  
 La fonction `_CrtDumpMemoryLeaks` détermine si une fuite de mémoire a eu lieu depuis le début de l'exécution du programme.  Lorsqu'une fuite est trouvée, les informations d'en\-tête du débogage pour tous les objets de la pile sont jetés dans un formulaire lisible par l'utilisateur.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtDumpMemoryLeaks` sont supprimés pendant le prétraitement.  
  
 `_CrtDumpMemoryLeaks` est souvent appelé à la fin de l'exécution du programme pour vérifier que la mémoire allouée par l'application a été libérée.  La fonction peut être appelée automatiquement à l'arrêt du programme en activation du champ de bits `_CRTDBG_LEAK_CHECK_DF` de l'indicateur [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) à la fonction [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  
  
 `_CrtDumpMemoryLeaks` appelle [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) pour obtenir l'état actuel de la pile puis analyse l'état des blocs qui n'ont pas été libérés.  Lorsqu'un bloc non\-libéré apparaît, `_CrtDumpMemoryLeaks` appelle [\_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) pour faire un dump des informations pour tous les objets alloués dans le tas depuis le début de l'exécution du programme.  
  
 Par défaut, les blocs internes du runtime C \(`_CRT_BLOCK`\) ne sont pas inclus dans les opérations d'image mémoire.  La fonction [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour mettre à 1 le bit `_CRTDBG_CHECK_CRT_DF` de `_crtDbgFlag` pour inclure ces blocs dans le processus de détection des fuites.  
  
 Pour plus d'informations sur les fonctions d'état du tas et la structure de `_CrtMemState`, consultez [Fonctions de création de rapports sur l'état du tas](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Pour plus d'informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour un exemple d'utilisation de `_CrtDumpMemoryLeaks`, consultez [crt\_dbg1](http://msdn.microsoft.com/fr-fr/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)