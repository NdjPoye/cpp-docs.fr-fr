---
title: _lfind_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _lfind_s
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
- lfind_s
- _lfind_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- keys, finding in arrays
- lfind_s function
- arrays [CRT], searching
- searching, linear
- _lfind_s function
ms.assetid: f1d9581d-5c9d-4222-a31c-a6dfafefa40d
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c50893f1dc73db9f928eaea346a381d1bd991d2f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="lfinds"></a>_lfind_s
Effectue une recherche linéaire portant sur la clé spécifiée. Version de [_lfind](../../c-runtime-library/reference/lfind.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `key`  
 Objet à rechercher.  
  
 `base`  
 Pointeur désignant la base de données de recherche.  
  
 `num`  
 Nombre d’éléments de tableau.  
  
 `size`  
 Taille des éléments de tableau en octets.  
  
 `compare`  
 Pointeur désignant la routine de comparaison. Le premier paramètre est le pointeur `context`. Le deuxième paramètre est un pointeur désignant la clé pour la recherche. Le troisième paramètre est un pointeur désignant l’élément de tableau à comparer à la clé.  
  
 `context`  
 Pointeur désignant un objet accessible dans la fonction de comparaison.  
  
## <a name="return-value"></a>Valeur de retour  
 Si la clé est trouvée, `_lfind_s` retourne un pointeur désignant l’élément du tableau à `base` qui correspond à `key`. Si la clé est introuvable, `_lfind_s` retourne `NULL`.  
  
 Si des paramètres non valides sont passés à la fonction, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|clé|de base|compare|num|size|errno|  
|---------|----------|-------------|---------|----------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|zéro|`EINVAL`|  
|any|any|`NULL`|an|any|`EINVAL`|  
  
## <a name="remarks"></a>Notes  
 La fonction `_lfind_s` effectue une recherche linéaire portant sur la valeur `key` dans un tableau de `num` éléments, chacun d’une taille de `width` octets. Contrairement à `bsearch_s`, `_lfind_s` ne nécessite pas que le tableau soit trié. L’argument `base` est un pointeur désignant la base du tableau à explorer. L’argument `compare` est un pointeur désignant une routine fournie par l’utilisateur qui compare deux éléments de tableau, puis retourne une valeur spécifiant leur relation. `_lfind_s` appelle la routine `compare` une ou plusieurs fois pendant la recherche, passant le pointeur `context` et les pointeurs désignant deux éléments de tableau à chaque appel. La routine `compare` doit comparer les éléments, puis retourner une valeur différente de zéro (les éléments sont différents) ou 0 (les éléments sont identiques).  
  
 `_lfind_s` est semblable à `_lfind`, à ceci près que le pointeur `context` est ajouté aux arguments de la fonction de comparaison et à la liste des paramètres de la fonction. Le pointeur `context` peut être utile si la structure de données explorée fait partie d’un objet et que la fonction `compare` doit accéder aux membres de l’objet. La fonction `compare` peut effectuer un cast du pointeur void vers le type d’objet approprié et accéder aux membres de cet objet. L’ajout du paramètre `context` sécurise `_lfind_s`, car un contexte supplémentaire peut être utilisé pour éviter les bogues de réentrance associés à l’utilisation de variables statiques et rendre les données accessibles à la fonction `compare`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_lfind_s`|\<search.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
weit found  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lsearch_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort_s](../../c-runtime-library/reference/qsort-s.md)   
 [_lfind](../../c-runtime-library/reference/lfind.md)
