---
title: "bsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "bsearch_s"
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
  - "bsearch_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux [CRT], recherche binaire"
  - "bsearch_s (fonction)"
ms.assetid: d5690d5e-6be3-4f1d-aa0b-5ca6dbded276
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# bsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche binaire dans un tableau trié. Il s’agit d’une version de [bsearch](../../c-runtime-library/reference/bsearch.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
void *bsearch_s(   
   const void *key,  
   const void *base,  
   size_t num,  
   size_t width,  
   int ( __cdecl *compare ) ( void *, const void *key, const void *datum),  
   void * context  
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
 Fonction de rappel qui compare deux éléments. Le premier argument est le pointeur `context`. Le deuxième argument est un pointeur vers le `key` pour la recherche. Le troisième argument est un pointeur vers l’élément de tableau à comparer à `key`.  
  
 `context`  
 Pointeur vers un objet accessible dans la fonction de comparaison.  
  
## Valeur de retour  
 `bsearch_s` retourne un pointeur vers une occurrence de`key` du tableau pointé par `base`. Si `key` est introuvable, la fonction retourne `NULL`. Si le tableau n’est pas trié par ordre croissant ou qu’il contient des enregistrements en double avec des clés identiques, le résultat est imprévisible.  
  
 Si des paramètres non valides sont passés à la fonction, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno`a la valeur `EINVAL` et la fonction retourne `NULL`. Pour plus d’informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Conditions d’erreur  
  
|||||||  
|-|-|-|-|-|-|  
|`key`|`base`|`compare`|`num`|`width`|`errno`|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|\= 0|`EINVAL`|  
|any|any|`NULL`|an|any|`EINVAL`|  
  
## Notes  
 La fonction `bsearch_s` effectue une recherche binaire dans un tableau trié de `num` éléments, chacun d’une taille de `width` octets. La valeur de `base` est un pointeur vers la base du tableau dans lequel effectuer la recherche, et `key` est la valeur recherchée. Le paramètre `compare` est un pointeur vers une routine fournie par l’utilisateur qui compare la clé demandée à un élément de tableau et retourne l’une des valeurs suivantes précisant leur relation :  
  
|Valeur retournée par la routine `compare`|Description|  
|-----------------------------------------------|-----------------|  
|\< 0|La clé est inférieure à l’élément de tableau.|  
|0|La clé est égale à l’élément de tableau.|  
|\> 0|La clé est supérieure à l’élément de tableau.|  
  
 Le pointeur `context` peut être utile si la structure de données faisant l’objet de la recherche fait partie d’un objet, et la fonction de comparaison doit accéder aux membres de l’objet. La fonction `compare` peut effectuer une conversion de type \(transtypage\) du pointeur void vers le type d’objet approprié et accéder aux membres de cet objet. L’ajout du paramètre `context` sécurise `bsearch_s`, car un contexte supplémentaire peut être utilisé pour éviter les bogues de réentrance associés à l’utilisation de variables statiques et rendre les données accessibles à la fonction `compare`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`bsearch_s`|\<stdlib.h\> et \<search.h\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## Exemple  
 Ce programme trie un tableau de chaînes avec [qsort\_s](../../c-runtime-library/reference/qsort-s.md) et utilise ensuite bsearch\_s pour rechercher le mot « cat ».  
  
```  
// crt_bsearch_s.cpp  
// This program uses bsearch_s to search a string array,  
// passing a locale as the context.  
// compile with: /EHsc  
#include <stdlib.h>  
#include <stdio.h>  
#include <search.h>  
#include <process.h>  
#include <locale.h>  
#include <locale>  
#include <windows.h>  
using namespace std;  
  
// The sort order is dependent on the code page.  Use 'chcp' at the  
// command line to change the codepage.  When executing this application,  
// the command prompt codepage must match the codepage used here:  
  
#define CODEPAGE_850  
  
#ifdef CODEPAGE_850  
#define ENGLISH_LOCALE "English_US.850"  
#endif  
  
#ifdef CODEPAGE_1252  
#define ENGLISH_LOCALE "English_US.1252"  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, char **str1, char **str2)  
{  
    char *s1 = *str1;  
    char *s2 = *str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
int main( void )  
{  
   char *arr[] = {"dog", "pig", "horse", "cat", "human", "rat", "cow", "goat"};  
  
   char *key = "cat";  
   char **result;  
   int i;  
  
   /* Sort using Quicksort algorithm: */  
   qsort_s( arr,  
            sizeof(arr)/sizeof(arr[0]),  
            sizeof( char * ),  
            (int (*)(void*, const void*, const void*))compare,  
            &locale(ENGLISH_LOCALE) );  
  
   for( i = 0; i < sizeof(arr)/sizeof(arr[0]); ++i )    /* Output sorted list */  
      printf( "%s ", arr[i] );  
  
   /* Find the word "cat" using a binary search algorithm: */  
   result = (char **)bsearch_s( &key,  
                                arr,  
                                sizeof(arr)/sizeof(arr[0]),  
                                sizeof( char * ),  
                                (int (*)(void*, const void*, const void*))compare,  
                                &locale(ENGLISH_LOCALE) );  
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
 <xref:System.Collections.ArrayList.BinarySearch%2A>  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)