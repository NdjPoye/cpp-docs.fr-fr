---
title: "_lfind_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lfind_s"
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
  - "lfind_s"
  - "_lfind_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_lfind_s (fonction)"
  - "tableaux (CRT), rechercher"
  - "clés, rechercher dans les tableaux"
  - "lfind_s (fonction)"
  - "recherche linéaire"
  - "rechercher, linéaires"
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# _lfind_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche linéaire pour la clé spécifiée.  Il s'agit de versions de [\_lfind](../../c-runtime-library/reference/lfind.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
void *_lfind_s(  
   const void *key,  
   const void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### Paramètres  
 `key`  
 Objet  à rechercher.  
  
 `base`  
 Pointeur vers la base de données de recherche.  
  
 `num`  
 Nombre d'éléments du tableau.  
  
 `size`  
 Taille des éléments du tableau en octets.  
  
 `compare`  
 Pointeur vers la routine de comparaison.  Le premier paramètre est le pointeur `context`.  Le deuxième paramètre est un pointeur vers la clé pour la recherche.  Le troisième paramètre est un pointeur vers un élément de tableau à comparer à la clé.  
  
 `context`  
 Un pointeur vers un objet, qui peut être accessible dans la fonction de comparaison.  
  
## Valeur de retour  
 Si la clé est trouvée, `_lfind_s` retourne un pointeur vers l'élément du tableau à `base`qui correspond à`key` .  Si la clé n'est pas trouvée`_lfind_s`retourne `NULL`.  
  
 Si des paramètres non valides sont transmis à la fonction, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  
  
### Conditions d'erreur  
  
|key|base|compare|num|taille|errno|  
|---------|----------|-------------|---------|------------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|zéro|`EINVAL`|  
|any|any|`NULL`|Un|any|`EINVAL`|  
  
## Notes  
 La fonction `_lfind_s` effectue une recherche séquentielle pour la valeur `key` dans un tableau d'éléments de `num`éléments, chacun de`width`octets.  Contrairement à `bsearch_s`, `_lfind_s` ne nécessite pas que le tableau soit trié.  L'argument `base` est un pointeur vers la base du tableau à trier.  La fonction `compare` est un pointeur vers une routine fournie à l'utilisateur, qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  `_lfind_s` appelle la routine `compare` à une ou plusieurs reprises lors de la recherche, en passant un pointeur `context` et des pointeurs à deux éléments de tableau à chaque appel.  La routine `compare` doit comparer les éléments puis retourner une valeur différente de zéro \(c'est\-à\-dire que les éléments sont différents\) ou 0 \(ce qui signifie les éléments sont identiques\).  
  
 `_lfind_s` est similaire à `_lfind` sauf quand à l'ajout du pointeur `context` aux arguments de la fonction de comparaison et de la liste des paramètres de la fonction.  Le pointeur `context` peut être utile si la structure de données recherchée fait partie d'un objet et que la fonction `compare` doit accéder à des membres de l'objet.  La fonction `compare` peut convertir le pointeur void au type d'objet approprié et accéder aux membres de cet objet.  L'ajout du pointeur `context` permet de rendre`_lfind_s` plus sécurisé car le contexte supplémentaire peut être utilisé pour éviter les bogues de reentrées associés à l'utilisation des variables statiques pour rendre les données disponibles à la fonction `compare`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lfind_s`|\<Rechercher\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_lfind_s.cpp  
// This program uses _lfind_s to search a string array,  
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
// Codepage 850 is the OEM codepage used by the command line,  
// so \x00e1 is the German Sharp S  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making it vulnerable to thread conflicts  
// (if this were a multithreaded program).  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char *s1 = *(char**)str1;  
    char *s2 = *(char**)str2;  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(  
       s1, s1+strlen(s1),  
       s2, s2+strlen(s2) );  
}  
  
void find_it( char *key, char *array[], unsigned int num, locale &loc )  
{  
   char **result = (char **)_lfind_s( &key, array,   
                      &num, sizeof(char *), compare, &loc );  
   if( result )  
      printf( "%s found\n", *result );  
   else  
      printf( "%s not found\n", key );  
}  
  
int main( )  
{  
   find_it( "weit", array1, sizeof(array1)/sizeof(char*), locale(GERMAN_LOCALE) );  
}  
```  
  
  **weit trouvé**   
## Équivalent .NET Framework  
 <xref:System.Collections.ArrayList.Contains%2A>  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort\_s](../../c-runtime-library/reference/qsort-s.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)