---
title: bsearch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- bsearch
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
- bsearch
dev_langs:
- C++
helpviewer_keywords:
- arrays [CRT], binary search
- bsearch function
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 431bb94e27397f8a0242c45db83e00250e5c82f3
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="bsearch"></a>bsearch
Effectue une recherche binaire dans un tableau trié. Une version plus sécurisée de cette fonction est disponible. Consultez [bsearch_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur vers la base de données de recherche.  
  
 `num`  
 Nombre d'éléments.  
  
 `width`  
 Largeur des éléments.  
  
 `compare`  
 Fonction de rappel qui compare deux éléments. Le premier est un pointeur vers la clé de la recherche et le deuxième est un pointeur vers l’élément de tableau à comparer à la clé.  
  
## <a name="return-value"></a>Valeur de retour  
 `bsearch` retourne un pointeur vers une occurrence de `key` du tableau pointé par `base`. Si `key` est introuvable, la fonction retourne `NULL`. Si le tableau n’est pas trié par ordre croissant ou qu’il contient des enregistrements en double avec des clés identiques, le résultat est imprévisible.  
  
## <a name="remarks"></a>Notes  
 La fonction `bsearch` effectue une recherche binaire dans un tableau trié de `num` éléments, chacun d’une taille de `width` octets. La valeur de `base` est un pointeur vers la base du tableau dans lequel effectuer la recherche, et `key` est la valeur recherchée. Le paramètre `compare` est un pointeur vers une routine fournie par l’utilisateur qui compare la clé demandée à un élément de tableau et retourne l’une des valeurs suivantes précisant leur relation :  
  
|Valeur retournée par la routine `compare`|Description|  
|-----------------------------------------|-----------------|  
|\< 0|La clé est inférieure à l’élément de tableau.|  
|0|La clé est égale à l’élément de tableau.|  
|> 0|La clé est supérieure à l’élément de tableau.|  
  
 Cette fonction valide ses paramètres. Si `compare`, `key` ou `num` a la valeur `NULL`, ou si `base` a la valeur `NULL` et que *`num` est différent de zéro, ou si `width` est égal à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`bsearch`|\<stdlib.h> et \<search.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Ce programme trie un tableau de chaînes avec qsort et utilise ensuite bsearch pour rechercher le mot « cat ».  
  
```  
// crt_bsearch.c  
#include <search.h>  
#include <string.h>  
#include <stdio.h>  
  
int compare( char **arg1, char **arg2 )  
{  
   /* Compare all of both strings: */  
   return _strcmpi( *arg1, *arg2 );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
   char **result;  
   char *key = "cat";  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort( (void *)arr, sizeof(arr)/sizeof(arr[0]), sizeof( char * ), (int (*)(const   
   void*, const void*))compare );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch( (char *) &key, (char *)arr, sizeof(arr)/sizeof(arr[0]),  
                              sizeof( char * ), (int (*)(const void*, const void*))compare );  
   if( result )  
      printf( "\n%s found at %Fp\n", *result, result );  
   else  
      printf( "\nCat not found!\n" );  
}  
```  
  
```Output  
cat cow dog goat horse human pig rat  
cat found at 002F0F04  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)
