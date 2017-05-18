---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6a4a5c78b4301158d1f0d23f588d6afe353104a0
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

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
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_CrtDumpMemoryLeaks`, consultez [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
