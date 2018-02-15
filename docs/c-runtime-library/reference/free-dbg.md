---
title: _free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa3df169a968313d2a29fbf9c08643748d3196d8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="freedbg"></a>_free_dbg
Libère un bloc de mémoire dans le tas (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `userData`  
 Pointeur désignant le bloc de mémoire alloué à libérer.  
  
 `blockType`  
 Type de bloc de mémoire alloué à libérer : `_CLIENT_BLOCK`, `_NORMAL_BLOCK` ou `_IGNORE_BLOCK`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_free_dbg` est une version de débogage de la fonction [free](../../c-runtime-library/reference/free.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_free_dbg` est réduit à un appel à `free`. `free` et `_free_dbg` libèrent toutes deux un bloc de mémoire dans le tas de base, mais `_free_dbg` gère deux fonctionnalités de débogage : la capacité à conserver les blocs libérés dans la liste liée du tas pour simuler des conditions de mémoire insuffisante et un paramètre de type de bloc pour libérer des types d’allocations spécifiques.  
  
 `_free_dbg` effectue une vérification de validité sur tous les fichiers et emplacements de blocs spécifiés avant de procéder à la libération. Il n'est pas prévu que l'application fournisse ces informations. Quand un bloc de mémoire est libéré, le gestionnaire de tas de débogage vérifie automatiquement l'intégrité des mémoires tampons de chaque côté de la partie utilisateur et émet un rapport d'erreurs si un remplacement a eu lieu. Si le champ de bits `_CRTDBG_DELAY_FREE_MEM_DF` de l’indicateur [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) est défini, le bloc libéré est renseigné avec la valeur 0xDD, le type de bloc `_FREE_BLOCK` lui est affecté et il est conservé dans la liste liée du tas des blocs de mémoire.  
  
 Si une erreur se produit pendant la libération de la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de la défaillance. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_free_dbg`, consultez [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)