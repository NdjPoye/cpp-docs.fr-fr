---
title: "_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l | Microsoft Docs"
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
  - "_strlwr_l"
  - "_strlwr"
  - "_wcslwr_l"
  - "_mbslwr_l"
  - "_wcslwr"
  - "_mbslwr"
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
apitype: "DLLExport"
f1_keywords: 
  - "_strlwr"
  - "wcslwr_l"
  - "_ftcslwr"
  - "mbslwr_l"
  - "_mbslwr"
  - "_wcslwr"
  - "strlwr_l"
  - "_tcslwr"
  - "mbslwr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcslwr (fonction)"
  - "_mbslwr (fonction)"
  - "_mbslwr_l (fonction)"
  - "_strlwr (fonction)"
  - "_strlwr_l (fonction)"
  - "_tcslwr (fonction)"
  - "_tcslwr_l (fonction)"
  - "_wcslwr (fonction)"
  - "_wcslwr_l (fonction)"
  - "casse, convertir"
  - "convertir la casse"
  - "convertir la casse, CRT (fonctions)"
  - "ftcslwr (fonction)"
  - "mbslwr (fonction)"
  - "mbslwr_l (fonction)"
  - "conversion de chaînes (C++), casse"
  - "chaînes (C++), casse"
  - "chaînes (C++), convertir la casse"
  - "strlwr_l (fonction)"
  - "tcslwr (fonction)"
  - "tcslwr_l (fonction)"
  - "wcslwr_l (fonction)"
ms.assetid: d279181d-2e7d-401f-ab44-6e7c2786a046
caps.latest.revision: 36
caps.handback.revision: 34
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en minuscules.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md).  
  
> [!IMPORTANT]
>  `_mbslwr` et `_mbslwr_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_strlwr(  
   char * str  
);  
wchar_t *_wcslwr(  
   wchar_t * str  
);  
unsigned char *_mbslwr(  
   unsigned char * str  
);  
char *_strlwr_l(  
   char * str,  
   _locale_t locale  
);  
wchar_t *_wcslwr_l(  
   wchar_t * str,  
   _locale_t locale  
);  
unsigned char *_mbslwr_l(  
   unsigned char * str,  
   _locale_t locale   
);  
template <size_t size>  
char *_strlwr(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wcslwr(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
unsigned char *_mbslwr(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
char *_strlwr_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
wchar_t *_wcslwr_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
unsigned char *_mbslwr_l(  
   unsigned char (&str)[size],  
   _locale_t locale   
); // C++ only  
```  
  
#### Paramètres  
 `str`  
 Chaîne de caractères terminée par le caractère NULL à convertir en minuscules.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers la chaîne convertie.  La modification étant effectuée en place, le pointeur retourné est identique au pointeur passé comme argument d'entrée.  Aucune valeur de retour n'est réservée pour indiquer une erreur.  
  
## Notes  
 La fonction `_strlwr` convertit toutes les lettres majuscules dans `str` en minuscules comme spécifié par le paramètre de catégorie `LC_CTYPE` des paramètres régionaux.  Les autres caractères ne sont pas affectés.  Pour plus d'informations sur `LC_CTYPE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour leur comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l`  sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Les fonctions `_wcslwr` et `_mbslwr` sont à caractère larges et à caractères multi\-octets de `_strlwr`.  L'argument et la valeur de retour de `_wcslwr` sont des chaînes à caractères larges ; ceux de `_mbslwr` sont des chaînes de caractères multi\-octets.  Ces trois fonctions se comportent sinon de façon identique.  
  
 Si `str` est un pointeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent la chaine originale et donnent à `errno` la valeur `EINVAL`.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tcslwr`|`_strlwr`|`_mbslwr`|`_wcslwr`|  
|`_tcslwr_l`|`_strlwr_l`|`_mbslwr_l`|`_wcslwr_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_strlwr`, `_strlwr_l`|\<string.h\>|  
|`_wcslwr`, `_wcslwr_l`|\<string.h\> ou \<wchar.h\>|  
|`_mbslwr`, `_mbslwr_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strlwr.c  
// compile with: /W3  
// This program uses _strlwr and _strupr to create  
// uppercase and lowercase copies of a mixed-case string.  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The String to End All Strings!";  
   char * copy1 = _strdup( string ); // make two copies  
   char * copy2 = _strdup( string );  
  
   _strlwr( copy1 ); // C4996  
   // Note: _strlwr is deprecated; consider using _strlwr_s instead  
   _strupr( copy2 ); // C4996  
   // Note: _strupr is deprecated; consider using _strupr_s instead  
  
   printf( "Mixed: %s\n", string );  
   printf( "Lower: %s\n", copy1 );  
   printf( "Upper: %s\n", copy2 );  
  
   free( copy1 );  
   free( copy2 );  
}  
```  
  
  **Mixte : La Chaîne Pour Terminer Toutes Les Chaînes \!**  
**Minuscules : la chaîne pour terminer toutes les chaînes \!**  
**Majuscule : LA CHAÎNE POUR TERMINER TOUTES LES CHAÎNES \!**   
## Équivalent .NET Framework  
 [System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)