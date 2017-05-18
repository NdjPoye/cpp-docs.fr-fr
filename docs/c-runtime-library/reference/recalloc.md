---
title: _recalloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _recalloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _recalloc
- recalloc
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ae78e17f66448de46e36ea7d6dc6e3121b306c68
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="recalloc"></a>_recalloc
Combinaison de `realloc` et `calloc`. Réalloue un tableau en mémoire et initialise ses éléments à 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur désignant le bloc de mémoire précédemment alloué.  
  
 `num`  
 Nombre d'éléments.  
  
 `size`  
 Longueur en octets de chaque élément.  
  
## <a name="return-value"></a>Valeur de retour  
 `_recalloc` retourne un pointeur `void` vers le bloc de mémoire réalloué (et éventuellement déplacé).  
  
 Si la quantité de mémoire disponible ne suffit pas à agrandir le bloc à la taille donnée, le bloc d’origine reste inchangé, et `NULL` est retourné.  
  
 Si la taille demandée est égale à zéro, le bloc désigné par `memblock` est libéré ; la valeur de retour est `NULL`, et `memblock` pointe vers un bloc libéré.  
  
 La valeur de retour pointe vers un espace de stockage qui est obligatoirement aligné correctement pour le stockage de tout type d'objet. Pour obtenir un pointeur vers un autre type que `void`, utilisez un cast de type sur la valeur de retour.  
  
## <a name="remarks"></a>Notes  
 La fonction `_recalloc` modifie la taille d’un bloc de mémoire alloué. L’argument `memblock` pointe vers le début du bloc de mémoire. Si `memblock` est `NULL`, `_recalloc` se comporte de la même façon que [calloc](../../c-runtime-library/reference/calloc.md) et alloue un nouveau bloc de `num`  *  `size` octets. Chaque élément est initialisé à 0. Si `memblock` n’a pas la valeur `NULL`, il doit correspondre à un pointeur retourné par un appel précédent à `calloc`, [malloc](../../c-runtime-library/reference/malloc.md) ou [realloc](../../c-runtime-library/reference/realloc.md).  
  
 Sachant que le nouveau bloc peut se trouver à un nouvel emplacement de mémoire, il n’est pas garanti que le pointeur retourné par `_recalloc` soit le pointeur transmis via l’argument `memblock`.  
  
 `_recalloc` affecte à `errno` la valeur `ENOMEM` si l’allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`. Pour plus d’informations sur ce code d’erreur et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `recalloc` appelle `realloc` pour utiliser la fonction C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) dans le but de définir le mode de nouveau gestionnaire. Le mode de nouveau gestionnaire indique si, en cas d’échec, `realloc` doit appeler la routine de nouveau gestionnaire, telle qu’elle est définie par [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Par défaut, `realloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec d’allocation de mémoire. Vous pouvez remplacer ce comportement par défaut de sorte que, quand _`_recalloc` ne parvient pas à allouer de la mémoire, `realloc` appelle la routine de nouveau gestionnaire de la même façon que l’opérateur `new` quand il échoue pour la même raison. Pour remplacer la valeur par défaut, appelez  
  
```  
_set_new_mode(1)  
```  
  
 au début de votre programme, ou créez un lien avec NEWMODE.OBJ.  
  
 Lorsque l’application est liée à une version debug des bibliothèques Runtime C, `_recalloc` se résout en [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md). Pour plus d’informations sur la gestion du tas pendant le processus de débogage, consultez [Tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_recalloc` est marqué `__declspec(noalias)` et `__declspec(restrict)`, ce qui signifie que la fonction ne peut pas modifier les variables globales et que le pointeur retourné n’a pas d’alias. Pour plus d’informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h> et \<malloc.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Options de lien](../../c-runtime-library/link-options.md)
