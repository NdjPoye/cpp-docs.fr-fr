---
title: _CrtDoForAllClientObjects | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: df96a24b04473099daaca29472f90c9770181e82
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
Appelle une fonction fournie par l'application pour tous les types `_CLIENT_BLOCK` du tas (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pfn`  
 Pointeur vers la fonction de rappel de la fonction fournie par l'application. Le premier paramètre de cette fonction pointe vers les données. Le second paramètre est le pointeur de contexte qui est passé à l'appel à `_CrtDoForAllClientObjects`.  
  
 `context`  
 Pointeur vers le contexte fourni par l'application à passer à la fonction fournie par l'application.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtDoForAllClientObjects` recherche dans la liste liée du tas des blocs de mémoire avec le type `_CLIENT_BLOCK` et appelle la fonction fournie par l'application quand un bloc de ce type est trouvé. Le bloc trouvé et le paramètre `context` sont passés comme arguments à la fonction fournie par l'application. Pendant le débogage, une application peut effectuer le suivi d'un groupe spécifique d'allocations en appelant de façon explicite les fonctions du tas de débogage pour allouer la mémoire et en indiquant que le type de bloc `_CLIENT_BLOCK` doit être affecté aux blocs. Il est alors possible d'assurer le suivi de ces blocs séparément ainsi que de créer des rapports correspondants différents pendant la création de rapports sur la détection des fuites et l'état de la mémoire.  
  
 Si le champ de bits `_CRTDBG_ALLOC_MEM_DF` de l’indicateur [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) n’est pas activé, `_CrtDoForAllClientObjects` se termine immédiatement. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtDoForAllClientObjects` sont supprimés lors du prétraitement.  
  
 Pour plus d’informations sur le type `_CLIENT_BLOCK` et la façon dont il peut être utilisé par d’autres fonctions de débogage, consultez [Types of blocks on the debug heap](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
 Si `pfn` a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, [errno, _doserrno, _sys_errlist, et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ont la valeur `EINVAL` et la fonction retourne le contrôle.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>, \<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** uniquement les versions de débogage des bibliothèques Runtime C.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)
