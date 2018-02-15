---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f71e37da509d4e8dd05c5a41afa9fe539294347
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
Vide tous les blocs de mémoire dans le tas de débogage quand une fuite de mémoire s’est produite (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `_CrtDumpMemoryLeaks` retourne TRUE si une fuite de mémoire est trouvée. Dans le cas contraire, la fonction retourne FALSE.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtDumpMemoryLeaks` détermine si une fuite de mémoire a eu lieu depuis le début de l’exécution du programme. Quand une fuite est détectée, les informations d’en-tête de débogage pour tous les objets du tas sont exportées dans un format lisible par l’utilisateur. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtDumpMemoryLeaks` sont supprimés durant le prétraitement.  
  
 `_CrtDumpMemoryLeaks` est fréquemment appelé à la fin de l’exécution du programme pour vérifier que toute la mémoire allouée par l’application a été libérée. La fonction peut être appelée automatiquement à la fin du programme en activant le champ de bits `_CRTDBG_LEAK_CHECK_DF` de l’indicateur [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) à l’aide de la fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  
  
 `_CrtDumpMemoryLeaks` appelle [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) pour obtenir l’état actuel du tas, puis vérifie l’état des blocs qui n’ont pas été libérés. Quand un bloc non libéré est rencontré, `_CrtDumpMemoryLeaks` appelle [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) pour vider les informations de tous les objets alloués dans le tas à partir du début de l’exécution du programme.  
  
 Par défaut, les blocs runtime C internes (`_CRT_BLOCK`) ne sont pas inclus dans les opérations relatives au vidage de la mémoire. La fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour activer la partie `_CRTDBG_CHECK_CRT_DF` de `_crtDbgFlag` afin d’inclure ces blocs dans le processus de détection des fuites.  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState` , consultez [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_CrtDumpMemoryLeaks`, consultez [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)