---
title: _aligned_free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3522cd33098484194fec8158b26577b9e01dfe62
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
Libère un bloc de mémoire qui a été alloué avec [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ou [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur vers le bloc de mémoire qui a été retourné à la fonction `_aligned_malloc` ou `_aligned_offset_malloc`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_aligned_free_dbg` est une version de débogage de la fonction [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, chaque appel à `_aligned_free_dbg` est réduit à un appel à `_aligned_free`. Les deux `_aligned_free` et `_aligned_free_dbg` libérer un bloc de mémoire dans le tas de base, mais `_aligned_free_dbg` prend en charge une fonctionnalité de débogage : la capacité à conserver libérés blocs dans la liste de liée du tas pour simuler des conditions de mémoire insuffisante.  
  
 `_aligned_free_dbg` effectue une vérification de validité sur tous les fichiers et emplacements de blocs spécifiés avant de procéder à la libération. Il n'est pas prévu que l'application fournisse ces informations. Quand un bloc de mémoire est libéré, le gestionnaire de tas de débogage vérifie automatiquement l'intégrité des mémoires tampons de chaque côté de la partie utilisateur et émet un rapport d'erreurs si un remplacement a eu lieu. Si le champ de bits `_CRTDBG_DELAY_FREE_MEM_DF` de l’indicateur [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) est défini, le bloc libéré est renseigné avec la valeur 0xDD, le type de bloc `_FREE_BLOCK` lui est affecté et il est conservé dans la liste liée du tas des blocs de mémoire.  
  
 Si une erreur se produit pendant la libération de la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de la défaillance. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)
