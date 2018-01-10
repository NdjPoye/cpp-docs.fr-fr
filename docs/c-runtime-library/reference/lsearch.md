---
title: _lsearch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _lsearch
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
- _lsearch
- lsearch
dev_langs: C++
helpviewer_keywords:
- _lsearch function
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- linear searches
- searching, linear
- lsearch function
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ffb2c0ec3547278f048855bb72a2e4ae1bb00287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="lsearch"></a>_lsearch
Effectue une recherche linéaire portant sur une valeur ; l’ajoute en fin de liste si elle est introuvable. Une version plus sécurisée de cette fonction est disponible. Consultez [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur désignant la base du tableau à explorer.  
  
 `num`  
 Nombre d'éléments.  
  
 `width`  
 Largeur de chaque élément du tableau.  
  
 `compare`  
 Pointeur désignant la routine de comparaison. Le premier paramètre est un pointeur désignant la clé pour la recherche. Le second paramètre est un pointeur désignant un élément de tableau à comparer à la clé.  
  
## <a name="return-value"></a>Valeur de retour  
 Si la clé est trouvée, `_lsearch` retourne un pointeur désignant l’élément du tableau à `base` qui correspond à `key`. Si la clé est introuvable, `_lsearch` retourne un pointeur désignant l’élément qui vient d’être ajouté à la fin du tableau.  
  
## <a name="remarks"></a>Notes  
 La fonction `_lsearch` effectue une recherche linéaire portant sur la valeur `key` dans un tableau de `num` éléments, chacun d’une taille de `width` octets. Contrairement à `bsearch`, `_lsearch` ne nécessite pas que le tableau soit trié. Si `key` n’est pas trouvé, `_lsearch` l’ajoute à la fin du tableau et incrémente `num`.  
  
 L’argument `compare` est un pointeur désignant une routine fournie par l’utilisateur qui compare deux éléments de tableau et retourne une valeur spécifiant leur relation. `_lsearch` appelle la routine `compare` une ou plusieurs fois pendant la recherche, passant les pointeurs désignant deux éléments de tableau à chaque appel. `compare` doit comparer les éléments et retourner une valeur différente de zéro (les éléments sont différents) ou 0 (les éléments sont identiques).  
  
 Cette fonction valide ses paramètres. Si `compare`, `key` ou `num` a la valeur `NULL`, ou si `base` a la valeur NULL et que *`num` est différent de zéro, ou si `width` est inférieur à zéro, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_lsearch`|\<search.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_lsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( const void *arg1, const void *arg2 );  
  
int main(void)  
{  
   char * wordlist[4] = { "hello", "thanks", "bye" };  
                            // leave room to grow...  
   int n = 3;  
   char **result;  
   char *key = "extra";  
   int i;  
  
   printf( "wordlist before _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
  
   result = (char **)_lsearch( &key, wordlist,   
                      &n, sizeof(char *), compare );  
  
   printf( "wordlist after _lsearch:" );  
   for( i=0; i<n; ++i ) printf( " %s", wordlist[i] );  
   printf( "\n" );  
}  
  
int compare(const void *arg1, const void *arg2 )  
{  
   return( _stricmp( * (char**)arg1, * (char**)arg2 ) );  
}  
```  
  
```Output  
wordlist before _lsearch: hello thanks bye  
wordlist after _lsearch: hello thanks bye extra  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)