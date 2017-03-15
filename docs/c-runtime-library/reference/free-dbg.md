---
title: _free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7ab13da1c51d75979656c4b70c4874566296e845
ms.lasthandoff: 02/24/2017

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
  
 Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les types de bloc d’allocation et sur leur utilisation, consultez [Types de bloc sur le tas de débogage](/visualstudio/debugger/crt-debug-heap-details). Pour plus d’informations sur les différences entre l’appel à une fonction de tas standard et sa version de débogage dans la build de débogage d’une application, consultez [Versions Debug des fonctions d’allocation du tas](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_free_dbg`, consultez [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)
