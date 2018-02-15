---
title: _CrtMemDumpAllObjectsSince | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17a8f1cd518c0864006d836f551d99554d3cdf24
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince
Vide les informations sur les objets dans le tas à partir du début de l’exécution du programme ou d’un état de tas spécifié (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `state`  
 Pointeur désignant l’état de tas à partir duquel commencer le vidage ou **NULL**.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtMemDumpAllObjectsSince` vide les informations d’en-tête de débogage des objets alloués dans le tas sous une forme lisible par l’utilisateur. Les informations de vidage permettent à l’application d’effectuer le suivi des allocations et de détecter les problèmes de mémoire. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemDumpAllObjectsSince` sont supprimés durant le prétraitement.  
  
 `_CrtMemDumpAllObjectsSince` utilise la valeur du paramètre `state` pour déterminer où lancer l’opération de vidage. Pour commencer le vidage à un état de tas spécifié, le paramètre `state` doit être un pointeur désignant une structure **_CrtMemState** qui a été renseignée par [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) avant l’appel de `_CrtMemDumpAllObjectsSince`. Quand `state` est **NULL**, la fonction commence le vidage au début de l’exécution du programme.  
  
 Si l’application a installé une fonction de raccordement de vidage en appelant [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md), chaque fois que `_CrtMemDumpAllObjectsSince` vide les informations sur un type de bloc `_CLIENT_BLOCK`, il appelle également la fonction de vidage fournie par l’application. Par défaut, les blocs runtime C internes (`_CRT_BLOCK`) ne sont pas inclus dans les opérations relatives au vidage de la mémoire. La fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour activer la partie `_CRTDBG_CHECK_CRT_DF` de **_crtDbgFlag** afin d’inclure ces blocs. En outre, les blocs marqués comme libérés ou ignorés (**_FREE_BLOCK**, **_IGNORE_BLOCK**) ne sont pas inclus dans le vidage de la mémoire.  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_CrtMemDumpAllObjectsSince`, consultez [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)