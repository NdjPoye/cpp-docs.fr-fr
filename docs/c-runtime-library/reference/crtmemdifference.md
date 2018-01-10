---
title: _CrtMemDifference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
dev_langs: C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ba4dc873fbb0e77f3b2f939c9d62533849dab76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crtmemdifference"></a>_CrtMemDifference
Compare deux états de la mémoire et retourne leurs différences (version Debug uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _CrtMemDifference(   
   _CrtMemState *stateDiff,  
   const _CrtMemState *oldState,  
   const _CrtMemState *newState   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stateDiff`  
 Pointeur vers une structure `_CrtMemState` utilisée pour stocker les différences entre deux états de la mémoire (retourné).  
  
 `oldState`  
 Pointeur vers un état antérieur de la mémoire (structure`_CrtMemState` ).  
  
 `newState`  
 Pointeur vers un état postérieur de la mémoire (structure`_CrtMemState` ).  
  
## <a name="return-value"></a>Valeur de retour  
 Si les états de la mémoire sont très différents, `_CrtMemDifference` retourne la valeur TRUE. Dans le cas contraire, la fonction retourne FALSE.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtMemDifference` compare `oldState` et `newState` , puis stocke leurs différences dans `stateDiff`, qui peut ensuite être utilisé par l’application pour détecter les fuites de mémoire et autres problèmes liés à cette dernière. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemDifference` sont supprimés durant le prétraitement.  
  
 `newState` et `oldState` doivent représenter chacun un pointeur valide vers une structure `_CrtMemState` , définie dans Crtdbg.h, qui a été rempli par [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) avant l’appel de `_CrtMemDifference`. `stateDiff` doit être un pointeur vers une instance allouée au préalable de la structure `_CrtMemState` . Si `stateDiff`, `newState` ou `oldState` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, _doserrno, _sys_errlist, et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ont la valeur `EINVAL` et la fonction retourne FALSE.  
  
 `_CrtMemDifference` compare les valeurs de champ `_CrtMemState` des blocs de `oldState` à celles de `newState`, puis stocke le résultat dans `stateDiff`. Quand le nombre de types de bloc alloués ou le nombre total de blocs alloués pour chaque type diffère entre les deux états de la mémoire, ces états sont considérés comme très différents. La différence entre la quantité maximale allouée simultanément pour les deux états, et la différence entre les allocations totales pour les deux états sont également stockées dans `stateDiff`.  
  
 Par défaut, les blocs runtime C internes (`_CRT_BLOCK`) ne sont pas inclus dans les opérations relatives à l’état de la mémoire. La fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour activer la partie `_CRTDBG_CHECK_CRT_DF` de `_crtDbgFlag` afin d’inclure ces blocs dans la détection des fuites et les autres opérations relatives à l’état de la mémoire. Les blocs de mémoire libérés (`_FREE_BLOCK`) n’amènent pas `_CrtMemDifference` à retourner la valeur TRUE.  
  
 Pour plus d’informations sur les fonctions d’état du tas et la structure `_CrtMemState` , consultez [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_CrtMemDifference`|\<crtdbg.h>|\<errno.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)