---
title: _lsearch_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 4969a12a821040c007a43248dc15927ee9f6ab40
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="lsearchs"></a>_lsearch_s
Effectue une recherche linéaire portant sur une valeur. Version de [_lsearch](../../c-runtime-library/reference/lsearch.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur désignant la base du tableau à explorer.  
  
 `num`  
 Nombre d'éléments.  
  
 `size`  
 Taille de chaque élément de tableau en octets.  
  
 `compare`  
 Pointeur désignant la routine de comparaison. Le deuxième paramètre est un pointeur désignant la clé pour la recherche. Le troisième paramètre est un pointeur désignant un élément de tableau à comparer à la clé.  
  
 `context`  
 Pointeur désignant un objet accessible dans la fonction de comparaison.  
  
## <a name="return-value"></a>Valeur de retour  
 Si `key` est trouvé, `_lsearch_s` retourne un pointeur désignant l’élément du tableau à `base` qui correspond à `key`. Si `key` est introuvable, `_lsearch_s` retourne un pointeur désignant l’élément qui vient d’être ajouté à la fin du tableau.  
  
 Si des paramètres non valides sont passés à la fonction, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` est défini sur `EINVAL` et la fonction retourne `NULL`. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|zéro|`EINVAL`|  
|any|any|`NULL`|an|any|`EINVAL`|  
  
## <a name="remarks"></a>Notes  
 La fonction `_lsearch_s` effectue une recherche linéaire portant sur la valeur `key` dans un tableau de `num` éléments, chacun d’une taille de `width` octets. Contrairement à `bsearch_s`, `_lsearch_s` ne nécessite pas que le tableau soit trié. Si `key` n’est pas trouvé, `_lsearch_s` l’ajoute à la fin du tableau et incrémente `num`.  
  
 La fonction `compare` est un pointeur désignant une routine fournie par l’utilisateur qui compare deux éléments de tableau et retourne une valeur spécifiant leur relation. La fonction `compare` accepte également le pointeur désignant le contexte comme premier argument. `_lsearch_s` appelle `compare` une ou plusieurs fois pendant la recherche, passant les pointeurs désignant deux éléments de tableau à chaque appel. `compare` doit comparer les éléments, puis retourner une valeur différente de zéro (les éléments sont différents) ou 0 (les éléments sont identiques).  
  
 Le pointeur `context` peut être utile si la structure de données explorée fait partie d’un objet et que la fonction `compare` doit accéder aux membres de l’objet. Par exemple, le code dans la fonction `compare` peut effectuer un cast du pointeur void vers le type d’objet approprié et accéder aux membres de cet objet. L’ajout du pointeur `context` sécurise `_lsearch_s`, car un contexte supplémentaire peut être utilisé pour éviter les bogues de réentrance associés à l’utilisation de variables statiques et rendre les données accessibles à la fonction `compare`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)
