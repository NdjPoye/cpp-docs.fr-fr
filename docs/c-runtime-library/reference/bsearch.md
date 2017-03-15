---
title: "bsearch | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "bsearch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tableaux [CRT], recherche binaire"
  - "bsearch (fonction)"
ms.assetid: e0ad2f47-e7dd-49ed-8288-870457a14a2c
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche binaire dans un tableau trié. Une version plus sécurisée de cette fonction est disponible. Consultez [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md).  
  
## Syntaxe  
  
```  
void *bsearch(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) (const void *key, const void *datum)   
);  
```  
  
#### Paramètres  
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
  
## Valeur de retour  
 `bsearch` retourne un pointeur vers une occurrence de `key` du tableau pointé par `base`. Si `key` est introuvable, la fonction retourne `NULL`. Si le tableau n’est pas trié par ordre croissant ou qu’il contient des enregistrements en double avec des clés identiques, le résultat est imprévisible.  
  
## Notes  
 La fonction `bsearch` effectue une recherche binaire dans un tableau trié de `num` éléments, chacun d’une taille de `width` octets. La valeur de `base` est un pointeur vers la base du tableau dans lequel effectuer la recherche, et `key` est la valeur recherchée. Le paramètre `compare` est un pointeur vers une routine fournie par l’utilisateur qui compare la clé demandée à un élément de tableau et retourne l’une des valeurs suivantes précisant leur relation :  
  
|Valeur retournée par la routine `compare`|Description|  
|-----------------------------------------------|-----------------|  
|\< 0|La clé est inférieure à l’élément de tableau.|  
|0|La clé est égale à l’élément de tableau.|  
|\> 0|La clé est supérieure à l’élément de tableau.|  
  
 Cette fonction valide ses paramètres. Si `compare`, `key` ou `num` a la valeur `NULL`, ou si `base` a la valeur `NULL` et que \*`num` est différent de zéro, ou si `width` est égal à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`bsearch`|\<stdlib.h\> et \<search.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Ce programme trie un tableau de chaînes avec qsort et utilise ensuite bsearch pour rechercher le mot « cat ».  
  
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
cat cow dog goat horse human pig rat cat found at 002F0F04  
```  
  
## Équivalent .NET Framework  
 [System::Collections::ArrayList::BinarySearch](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)