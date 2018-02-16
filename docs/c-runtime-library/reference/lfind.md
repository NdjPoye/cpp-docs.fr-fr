---
title: _lfind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _lfind
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
- lfind
- _lfind
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- lfind function
- arrays [CRT], searching
- searching, linear
- finding keys in arrays
- _lfind function
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6df994306ad9a7d51d619a9bd409c021386a11
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="lfind"></a>_lfind
Effectue une recherche linéaire portant sur la clé spécifiée. Une version plus sécurisée de cette fonction est disponible. Consultez [_lfind_s](../../c-runtime-library/reference/lfind-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur désignant la base de données de recherche.  
  
 `num`  
 Nombre d’éléments de tableau.  
  
 `width`  
 Largeur des éléments du tableau.  
  
 `compare`  
 Pointeur désignant la routine de comparaison. Le premier paramètre est un pointeur désignant la clé pour la recherche. Le second paramètre est un pointeur désignant l’élément de tableau à comparer à la clé.  
  
## <a name="return-value"></a>Valeur de retour  
 Si la clé est trouvée, `_lfind` retourne un pointeur désignant l’élément du tableau à `base` qui correspond à `key`. Si la clé est introuvable, `_lfind` retourne `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_lfind` effectue une recherche linéaire portant sur la valeur `key` dans un tableau de `num` éléments, chacun d’une taille de `width` octets. Contrairement à `bsearch`, `_lfind` ne nécessite pas que le tableau soit trié. L’argument `base` est un pointeur désignant la base du tableau à explorer. L’argument `compare` est un pointeur désignant une routine fournie par l’utilisateur qui compare deux éléments de tableau, puis retourne une valeur spécifiant leur relation. `_lfind` appelle la routine `compare` une ou plusieurs fois pendant la recherche, passant les pointeurs désignant deux éléments de tableau à chaque appel. La routine `compare` doit comparer les éléments, puis retourner une valeur différente de zéro (les éléments sont différents) ou 0 (les éléments sont identiques).  
  
 Cette fonction valide ses paramètres. Si `compare`, `key` ou `num` a la valeur `NULL`, ou si `base` a la valeur NULL et que *`num` est différent de zéro, ou si `width` est inférieur à zéro, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_lfind`|\<search.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_lfind.c  
// This program uses _lfind to search a string array  
// for an occurrence of "hello".  
  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
  
int main( )  
{  
   char *arr[] = {"Hi", "Hello", "Bye"};  
   int n = sizeof(arr) / sizeof(char*);  
   char **result;  
   char *key = "hello";  
  
   result = (char **)_lfind( &key, arr,   
                      &n, sizeof(char *), compare );  
  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "hello not found!\n" );  
}  
```  
  
```Output  
Hello found  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)