---
title: qsort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- qsort
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- qsort
dev_langs:
- C++
helpviewer_keywords:
- qsort function
- quick-sort algorithm
- sorting arrays
- arrays [CRT], sorting
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a39f6edf9dfdf2130bfe9d00cc2a9453f48ad9f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="qsort"></a>qsort
Effectue un tri rapide. Il existe une version plus sécurisée de cette fonction. Consultez [qsort_s](../../c-runtime-library/reference/qsort-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `base`  
 Début du tableau cible.  
  
 `num`  
 Taille du tableau dans les éléments.  
  
 `width`  
 Taille d’élément en octets.  
  
 `compare`  
 Pointeur désignant une routine fournie par l’utilisateur qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  
  
## <a name="remarks"></a>Notes  
 La fonction `qsort` implémente un algorithme de tri rapide pour trier un tableau d’éléments `num`, chacun de `width` octets. L’argument `base` est un pointeur désignant la base du tableau à trier. `qsort` remplace ce tableau en utilisant les éléments triés.  
  
 `qsort` appelle la routine `compare` une ou plusieurs fois pendant le tri, et transmet les pointeurs à deux éléments de tableau à chaque appel.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 La routine compare les éléments et retourner l’une des valeurs suivantes.  
  
|Valeur de retour de la fonction compare|Description|  
|-----------------------------------|-----------------|  
|< 0|`elem1` inférieure à `elem2`|  
|0|`elem1` équivalent à `elem2`|  
|> 0|`elem1` supérieur à `elem2`|  
  
 Le tableau est trié par ordre croissant, comme défini par la fonction de comparaison. Pour trier un tableau par ordre décroissant, changez le sens de « supérieur à » et « inférieur à » dans la fonction de comparaison.  
  
 Cette fonction valide ses paramètres. Si `compare` ou `num` a la valeur `NULL` ou si `base` a la valeur `NULL` et que *`num` est différent de zéro, ou si `width` est inférieur à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne une valeur et `errno` prend la valeur `EINVAL`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h> et \<search.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_qsort.c  
// arguments: every good boy deserves favor  
  
/* This program reads the command-line  
 * parameters and uses qsort to sort them. It  
 * then displays the sorted arguments.  
 */  
  
#include <stdlib.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main( int argc, char **argv )  
{  
   int i;  
   /* Eliminate argv[0] from sort: */  
   argv++;  
   argc--;  
  
   /* Sort remaining args using Quicksort algorithm: */  
   qsort( (void *)argv, (size_t)argc, sizeof( char * ), compare );  
  
   /* Output sorted list: */  
   for( i = 0; i < argc; ++i )  
      printf( " %s", argv[i] );  
   printf( "\n" );  
}  
  
int compare( const void *arg1, const void *arg2 )  
{  
   /* Compare all of both strings: */  
   return _stricmp( * ( char** ) arg1, * ( char** ) arg2 );  
}  
```  
  
```Output  
boy deserves every favor good  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)