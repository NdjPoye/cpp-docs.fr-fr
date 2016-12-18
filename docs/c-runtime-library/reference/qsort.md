---
title: "qsort | Microsoft Docs"
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
  - "qsort"
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
  - "qsort"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "qsort, fonction"
  - "quick-sort, algorithme"
  - "tri de tableaux"
  - "tableaux [CRT], trier"
ms.assetid: d6cb33eb-d209-485f-8d41-229eb743c027
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# qsort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue un tri rapide.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [qsort\_s](../../c-runtime-library/reference/qsort-s.md).  
  
## Syntaxe  
  
```  
void qsort(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(const void *, const void *)   
);  
```  
  
#### Paramètres  
 `base`  
 Début du tableau cible.  
  
 `num`  
 Taille du tableau en éléments.  
  
 `width`  
 Taille des éléments en octets.  
  
 `compare`  
 Pointeur vers une routine fournie à l'utilisateur qui compare deux éléments du tableau et retourne une valeur qui indique leur relation.  
  
## Notes  
 La fonction `qsort` implémente un algorithme de tri rapide qui range un tableau de `num`éléments, chacun de`width`octets.  L'argument `base` est un pointeur vers la base du tableau à trier.  `qsort` reécrit sur ce tableau en utilisant les éléments rangés.  
  
 `qsort` appelle la routine `compare` une ou plusieurs fois lors du tri, et passe les pointeurs vers deux éléments de tableau à chaque appel.  
  
```  
compare( (void *) & elem1, (void *) & elem2 );  
```  
  
 La routine compare les éléments et retourne l'une des valeurs suivantes.  
  
|La fonction compare retourne une valeur|Description|  
|---------------------------------------------|-----------------|  
|\< 0|`elem1` inférieure à `elem2`|  
|0|`elem1` est équivalent à `elem2`|  
|\> 0|`elem1` supérieur à `elem2`|  
  
 La table est trié en ordre croissant, comme défini par la fonction de comparaison.  Pour trier une table par ordre décroissant, inverser le sens « supérieur à » et « inférieur à » de la fonction de comparaison.  
  
 Cette fonction valide ses paramètres.  Si `compare` ou `num` est `NULL`, ou si `base` est `NULL` et \*`num` est différent de zéro, ou si `width` est inférieure à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne \-1 et définit `errno` avec la valeur `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`qsort`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **le garçon mérite chaque privilège**   
## Équivalent .NET Framework  
 [System::Collections::ArrayList::Sort](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)