---
title: _CrtMemDifference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDifference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2d8cba0ada845e7e75bfe15945700a1385c8bcbb
ms.lasthandoff: 02/24/2017

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
  
 `newState` et `oldState` doivent représenter chacun un pointeur valide désignant une structure `_CrtMemState`, définie dans Crtdbg.h, qui a été remplie par [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) avant l’appel de `_CrtMemDifference`. `stateDiff` doit être un pointeur désignant une instance allouée au préalable de la structure `_CrtMemState`. Si `stateDiff`, `newState` ou `oldState` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, _doserrno, _sys_errlist, et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ont la valeur `EINVAL` et la fonction retourne FALSE.  
  
 `_CrtMemDifference` compare les valeurs de champ `_CrtMemState` des blocs de `oldState` à celles de `newState`, puis stocke le résultat dans `stateDiff`. Quand le nombre de types de bloc alloués ou le nombre total de blocs alloués pour chaque type diffère entre les deux états de la mémoire, ces états sont considérés comme très différents. La différence entre la quantité maximale allouée simultanément pour les deux états, et la différence entre les allocations totales pour les deux états sont également stockées dans `stateDiff`.  
  
 Par défaut, les blocs runtime C internes (`_CRT_BLOCK`) ne sont pas inclus dans les opérations relatives à l’état de la mémoire. La fonction [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) peut être utilisée pour activer la partie `_CRTDBG_CHECK_CRT_DF` de `_crtDbgFlag` afin d’inclure ces blocs dans la détection des fuites et les autres opérations relatives à l’état de la mémoire. Les blocs de mémoire libérés (`_FREE_BLOCK`) n’amènent pas `_CrtMemDifference` à retourner la valeur TRUE.  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_CrtMemDifference`|\<crtdbg.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)
