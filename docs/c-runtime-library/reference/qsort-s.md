---
title: "qsort_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "qsort_s"
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
  - "qsort_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), trier"
  - "qsort_s (fonction)"
  - "quick-sort (algorithme)"
  - "tri de tableaux"
ms.assetid: 6ee817b0-4408-4355-a5d4-6605e419ab91
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# qsort_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue un tri rapide.  Il s'agit de versions de [qsort](../../c-runtime-library/reference/qsort.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
void qsort_s(  
   void *base,  
   size_t num,  
   size_t width,  
   int (__cdecl *compare )(void *, const void *, const void *),  
   void * context  
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
 Fonction de comparaison.  Le premier argument est le pointeur `context`.  Le deuxième argument est un pointeur vers `key` pour la recherche.  Le troisième argument est un pointeur sur l'élément de tableau à comparer à `key`.  
  
 `context`  
 Un pointeur vers un contexte, qui peut être tout objet auquel la routine `compare` doit accéder.  
  
## Notes  
 La fonction `qsort_s` implémente un algorithme de tri rapide qui range un tableau de `num` éléments, chacun de `width` octets.  L'argument `base` est un pointeur vers la base du tableau à trier.  `qsort_s` remplace ce tableau avec les éléments triés.  L'argument `compare` est un pointeur vers une routine fournie à l'utilisateur, qui compare deux éléments de tableau et retourne une valeur qui spécifie leur relation.  `qsort_s` appelle la routine `compare` une ou plusieurs fois lors du tri, passant les pointeurs vers deux éléments de tableau à chaque appel:  
  
```  
compare( context, (void *) & elem1, (void *) & elem2 );  
```  
  
 La routine doit comparer les éléments puis retourner l'une des valeurs suivantes :  
  
|Valeur de retour|Description|  
|----------------------|-----------------|  
|\< 0|`elem1` inférieure à `elem2`|  
|0|`elem1` est équivalent à `elem2`|  
|\> 0|`elem1` supérieur à `elem2`|  
  
 La table est trié en ordre croissant, comme défini par la fonction de comparaison.  Pour trier une table par ordre décroissant, inverser le sens « supérieur à » et « inférieur à » de la fonction de comparaison.  
  
 Si des paramètres non valides sont transmis à la fonction, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, alors la fonction retourne et `errno` est affecté à la valeur `EINVAL`.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### Conditions d'erreur  
  
|key|base|compare|num|largeur|errno|  
|---------|----------|-------------|---------|-------------|-----------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|\<\= 0|`EINVAL`|  
|any|any|`NULL`|any|any|`EINVAL`|  
  
 `qsort_s` a le même comportement que `qsort` mais a le paramètre `context` et définit `errno`.  En passant un paramètre `context`, les fonctions de comparaison peuvent utiliser un pointeur d'objet pour accéder aux fonctionnalités de l'objet ou à d'autres informations inaccessibles via un pointeur d'élément.  L'ajout du paramètre `context` permet de rendre `qsort_s`plus sécurisé car `context` peut être utilisé pour éviter les bogues de réentrance introduits par l'utilisation de variables statiques pour rendre les informations partagées disponibles pour la fonction `compare`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`qsort_s`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'information de compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
 **Bibliothèques :** toutes les versions [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 L'exemple suivant montre comment utiliser le paramètre `context` dans la fonction `qsort_s` `` .  Le paramètre `context` facilite la réalisation de tri thread\-safe.  Au lieu d'utiliser des variables statiques qui doivent être synchronisées pour vérifier la sécurité des threads, passez un paramètre différent `context` dans chaque tri.  Dans cet exemple, un objet de paramètres régionaux est utilisé comme paramètre de `context`.  
  
```  
// crt_qsort_s.cpp  
// compile with: /EHsc /MT  
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
// so \x00e1 is the German Sharp S in that codepage and \x00a4  
// is the n tilde.  
  
char *array1[] = { "wei\x00e1", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00a4ol", "Espa\x00a4" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.850"  
#define SPANISH_LOCALE "Spanish_Spain.850"  
#define ENGLISH_LOCALE "English_US.850"  
  
#endif  
  
#ifdef CODEPAGE_1252  
   // If using codepage 1252 (ISO 8859-1, Latin-1), use \x00df  
   // for the German Sharp S and \x001f for the n tilde.  
char *array1[] = { "wei\x00df", "weis", "annehmen", "weizen", "Zeit",  
                   "weit" };  
char *array2[] = { "Espa\x00f1ol", "Espa\x00f1" "a", "espantado" };  
char *array3[] = { "table", "tableux", "tablet" };  
  
#define GERMAN_LOCALE "German_Germany.1252"  
#define SPANISH_LOCALE "Spanish_Spain.1252"  
#define ENGLISH_LOCALE "English_US.1252"  
  
#endif  
  
// The context parameter lets you create a more generic compare.  
// Without this parameter, you would have stored the locale in a  
// static variable, thus making sort_array vulnerable to thread  
// conflicts.  
  
int compare( void *pvlocale, const void *str1, const void *str2)  
{  
    char s1[256];  
    char s2[256];  
    strcpy_s(s1, 256, *(char**)str1);  
    strcpy_s(s2, 256, *(char**)str2);  
    _strlwr_s( s1, sizeof(s1) );  
    _strlwr_s( s2, sizeof(s2) );  
  
    locale& loc = *( reinterpret_cast< locale * > ( pvlocale));  
  
    return use_facet< collate<char> >(loc).compare(s1,   
       &s1[strlen(s1)], s2, &s2[strlen(s2)]);  
  
}  
  
void sort_array(char *array[], int num, locale &loc)  
{  
    qsort_s(array, num, sizeof(char*), compare, &loc);  
}  
  
void print_array(char *a[], int c)  
{  
   for (int i = 0; i < c; i++)  
     printf("%s ", a[i]);  
   printf("\n");  
  
}  
  
void sort_german(void * Dummy)  
{  
   sort_array(array1, 6, locale(GERMAN_LOCALE));  
}  
  
void sort_spanish(void * Dummy)  
{     
   sort_array(array2, 3, locale(SPANISH_LOCALE));       
}  
  
void sort_english(void * Dummy)  
{     
   sort_array(array3, 3, locale(ENGLISH_LOCALE));     
}  
  
int main( )  
{  
  
   int i;  
   HANDLE threads[3];  
  
   printf("Unsorted input:\n");  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
   // Create several threads that perform sorts in different  
   // languages at the same time.   
  
   threads[0] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_german , 0, NULL));  
   threads[1] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_spanish, 0, NULL));  
   threads[2] = reinterpret_cast<HANDLE>(  
                 _beginthread( sort_english, 0, NULL));  
  
   for (i = 0; i < 3; i++)  
   {  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
      {  
         printf("Error creating threads.\n");  
         exit(1);  
      }  
   }  
  
   // Wait until all threads have terminated.  
   WaitForMultipleObjects(3, threads, true, INFINITE);  
  
   printf("Sorted output: \n");  
  
   print_array(array1, 6);  
   print_array(array2, 3);  
   print_array(array3, 3);  
  
}  
```  
  
## Résultat de l'exemple  
  
```  
Unsorted input:  
weiß weis annehmen weizen Zeit weit   
Español España espantado   
table tableux tablet   
Sorted output:   
annehmen weiß weis weit weizen Zeit   
España Español espantado   
table tablet tableux  
```  
  
## Équivalent .NET Framework  
 <xref:System.Collections.ArrayList.Sort%2A>  
  
## Voir aussi  
 [Recherche et tri](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lsearch\_s](../../c-runtime-library/reference/lsearch-s.md)   
 [qsort](../../c-runtime-library/reference/qsort.md)