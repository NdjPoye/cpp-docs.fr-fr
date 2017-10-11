---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 59379d4916c8414717e886d6fea79e977d31836f
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
Vide les informations d’en-tête de débogage pour l’état du tas spécifié sous une forme lisible par l’utilisateur (version Debug uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `state`  
 Pointeur vers l’état du tas à vider.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtMemDumpStatistics` vide les informations d’en-tête de débogage pour l’état du tas spécifié sous une forme lisible par l’utilisateur. Les statistiques de vidage permettent à l’application d’effectuer le suivi des allocations, et de détecter les problèmes de mémoire. L’état de la mémoire peut contenir un état de tas spécifique, ou la différence entre deux états. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtMemDumpStatistics` sont supprimés durant le prétraitement.  
  
 La fonction `state` doit être un pointeur vers une structure `_CrtMemState` remplie par [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) ou retournée par [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) avant l’appel de `_CrtMemDumpStatistics` . Si `state` a la valeur `NULL`, le gestionnaire de paramètres non valide est appelé, comme décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et aucune action n’est retournée. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur les fonctions d’état du tas et sur la structure `_CrtMemState`, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-têtes facultatifs|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
