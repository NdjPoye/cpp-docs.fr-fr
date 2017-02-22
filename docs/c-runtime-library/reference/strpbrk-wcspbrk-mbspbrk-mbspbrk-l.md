---
title: "strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbspbrk"
  - "wcspbrk"
  - "_mbspbrk_l"
  - "strpbrk"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_fstrpbrk"
  - "_mbspbrk"
  - "strpbrk"
  - "_tcspbrk"
  - "_ftcspbrk"
  - "wcspbrk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fstrpbrk (fonction)"
  - "_ftcspbrk (fonction)"
  - "_mbspbrk (fonction)"
  - "_mbspbrk_l (fonction)"
  - "_tcspbrk (fonction)"
  - "jeux de caractères (C++), rechercher des caractères dans les chaînes"
  - "caractères (C++), rechercher dans les chaînes"
  - "fstrpbrk (fonction)"
  - "ftcspbrk (fonction)"
  - "mbspbrk (fonction)"
  - "mbspbrk_l (fonction)"
  - "chaînes (C++), analyser"
  - "strpbrk (fonction)"
  - "tcspbrk (fonction)"
  - "wcspbrk (fonction)"
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parcourt des chaînes en cherchant des caractères des jeux de caractères spécifiés.  
  
> [!IMPORTANT]
>  `_mbspbrk` et `_mbspbrk_l` ne peuvent pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne terminée par Null ayant déjà été parcourue.  
  
 `strCharSet`  
 Jeu de caractères se terminant par null.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Retourne un pointeur vers la première occurrence d'un caractère de `strCharSet` dans `str`, ou un pointeur `NULL` si les deux arguments de chaîne n'ont aucun caractère en commun.  
  
## Notes  
 La fonction `strpbrk` retourne un pointeur vers la première occurrence d'un caractère dans un `str` qui appartient au jeu de caractères dans `strCharSet`.  La recherche ne contient pas le caractères de fin null.  
  
 `wcspbrk` et `_mbspbrk` sont des versions à caractères élargis et à caractères multi\-octets de `strpbrk`.  Les arguments et la valeur de retour de `wcspbrk` sont des chaînes à caractères larges ; ceux de `_mbspbrk` sont des chaînes de caractères multioctets.  
  
 `_mbspbrk` valide ses paramètres.  Si `str` ou `strCharSet` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `_mbspbrk` renvoie `NULL` et attribue à `errno` la valeur `EINVAL`.  `strpbrk` et `wcspbrk` ne valident pas leurs paramètres.  Ces trois fonctions se comportent sinon de façon identique.  
  
 `_mbspbrk` est semblable à `_mbscspn` mais `_mbspbrk` retourne un pointeur plutôt qu'une valeur de type [size\_t](../../c-runtime-library/standard-types.md).  
  
 En C, ces fonctions acceptent un pointeur `const` comme premier argument.  En C\+\+, deux surcharges sont disponibles.  La surcharge acceptant un pointeur vers `const` retourne un pointeur vers `const` ; la version qui accepte un pointeur vers non\-`const` retourne un pointeur vers non\-`const`.  La macro \_CONST\_CORRECT\_OVERLOADS est définie si les versions `const` et non\-`const` de ces fonctions sont disponibles.  Si vous avez besoin d'un comportement non\-`const` pour les deux surcharges C\+\+, définissez le symbol \_CONST\_RETURN.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; la version avec le suffixe `_l` est identique, sauf qu'elle utilise à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**N\/A**|**N\/A**|`_mbspbrk_l`|**N\/A**|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strpbrk`|\<string.h\>|  
|`wcspbrk`|\<string.h\> ou \<wchar.h\>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
  **1 : Les 3 hommes et 2 garçons ont mangé 5 porcs**  
**2 : 3 hommes et 2 garçons ont mangé 5 porcs**  
**3 : 2 garçons ont mangé 5 porcs**  
**4 : 5 porcs**   
## Équivalent .NET Framework  
 [System::String::IndexOfAny](https://msdn.microsoft.com/en-us/library/system.string.indexofany.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)