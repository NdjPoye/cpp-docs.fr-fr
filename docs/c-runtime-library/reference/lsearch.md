---
title: "_lsearch | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch"
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
  - "_lsearch"
  - "lsearch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lsearch (fonction)"
  - "tableaux (CRT), rechercher"
  - "clés, rechercher dans les tableaux"
  - "recherches linéaires"
  - "lsearch (fonction)"
  - "rechercher, linéaires"
  - "valeurs, rechercher"
ms.assetid: 8200f608-159a-46f0-923b-1a37ee1af7e0
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lsearch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue une recherche linéaire pour une valeur ; l'ajoute à la fin de la liste si elle n'est pas trouvée.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md).  
  
## Syntaxe  
  
```  
void *_lsearch(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   unsigned int width,  
   int (__cdecl *compare)(const void *, const void *)   
);  
```  
  
#### Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur vers la base de la table à rechercher.  
  
 `num`  
 Nombre d'éléments  
  
 `width`  
 Largeur de chaque élément du tableau.  
  
 `compare`  
 Pointeur vers la routine de comparaison.  Le premier paramètre est un pointeur vers la clé pour la recherche.  Le second paramètre est un pointeur vers un élément de tableau à comparer à la clé.  
  
## Valeur de retour  
 Si la clé est trouvée, `_lsearch` retourne un pointeur vers l'élément du tableau à `base` qui correspond à `key` .  Si la clé n'est pas trouvée, `_lsearch` retourne un pointeur sur l'élément récemment ajouté à la fin du tableau.  
  
## Notes  
 La fonction `_lsearch` effectue une recherche séquentielle pour la valeur `key` dans un tableau d'éléments de `num` éléments, chacun de `width` octets.  Contrairement à `bsearch`, `_lsearch` ne nécessite pas que le tableau soit trié.  Si `key` est introuvable, `_lsearch` l'ajoute à la fin de la table et incrémente `num`.  
  
 L'argument `compare` est un pointeur vers une routine fournie à l'utilisateur, qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  `_lsearch` appelle la routine `compare` une ou plusieurs fois lors de la recherche, passant les pointeurs vers deux éléments de tableau à chaque appel:  `compare` doit comparer les éléments et retourner ou une valeur différente de zéro \(c'est\-à\-dire que les éléments sont différents\) ou 0 \(ce qui signifie les éléments sont identiques\).  
  
 Cette fonction valide ses paramètres.  Si `compare`, `key` ou `num` est `NULL`, ou si `base` est différent de zéro, et \*`num` est différent de zéro, ou si `width` est inférieure à zéro, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_lsearch`|\<Rechercher\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **liste de mots avant \_lsearch : bonjour merci au revoir**  
**liste de mots après \_lsearch : bonjour merci bye extra**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch](../../c-runtime-library/reference/bsearch.md)   
 [\_lfind](../../c-runtime-library/reference/lfind.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)