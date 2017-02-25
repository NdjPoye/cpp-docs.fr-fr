---
title: "lfind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind"
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
  - "lfind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lfind (fonction)"
ms.assetid: a40ece70-1674-4b75-94bd-9f57cfff18f2
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _lfind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche linéaire pour la clé spécifiée.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md).  
  
## Syntaxe  
  
```  
void *_lfind(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)  
);  
```  
  
#### Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur vers la base de données de recherche.  
  
 `num`  
 Nombre d'éléments du tableau.  
  
 `width`  
 Largeur des éléments de tableau.  
  
 `compare`  
 Pointeur vers la routine de comparaison.  Le premier paramètre est un pointeur vers la clé pour la recherche.  Le second paramètre est un pointeur vers un élément de tableau à comparer à la clé.  
  
## Valeur de retour  
 Si la clé est trouvée, `_lfind` retourne un pointeur vers l'élément du tableau à `base` qui correspond à `key` .  Si la clé n'est pas trouvée `_lfind` retourne `NULL`.  
  
## Notes  
 La fonction `_lfind` effectue une recherche séquentielle pour la valeur `key` dans un tableau d'éléments de `num` éléments, chacun de `width` octets.  Contrairement à `bsearch`, `_lfind` ne nécessite pas que le tableau soit trié.  L'argument `base` est un pointeur vers la base du tableau à trier.  La fonction `compare` est un pointeur vers une routine fournie à l'utilisateur, qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  `_lfind` appelle la routine `compare` une ou plusieurs fois lors de la recherche, passant les pointeurs vers deux éléments de tableau à chaque appel:  La routine `compare` doit comparer les éléments et puis retourner une valeur différente de zéro \(c'est\-à\-dire que les éléments sont différents\) ou 0 \(ce qui signifie les éléments sont identiques\).  
  
 Cette fonction valide ses paramètres.  Si `compare`, `key` ou `num` est `NULL`, ou si `base` est différent de zéro, et \*`num` est différent de zéro, ou si `width` est inférieure à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lfind`|\<Rechercher\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **Hello trouvé**   
## Équivalent .NET Framework  
 [System::Collections::ArrayList::Contains](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind\_s](../../c-runtime-library/reference/lfind-s.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)