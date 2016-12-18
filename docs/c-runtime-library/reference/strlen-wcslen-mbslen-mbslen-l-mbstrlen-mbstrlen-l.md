---
title: "strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l | Microsoft Docs"
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
  - "_mbslen"
  - "_mbslen_l"
  - "_mbstrlen"
  - "wcslen"
  - "_mbstrlen_l"
  - "strlen"
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
  - "_mbstrlen"
  - "wcslen"
  - "_tcslen"
  - "_ftcslen"
  - "strlen"
  - "_mbslen"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcslen (fonction)"
  - "_mbslen (fonction)"
  - "_mbslen_l (fonction)"
  - "_mbstrlen (fonction)"
  - "_mbstrlen_l (fonction)"
  - "_tcslen (fonction)"
  - "ftcslen (fonction)"
  - "longueurs, chaînes"
  - "mbslen (fonction)"
  - "mbslen_l (fonction)"
  - "mbstrlen (fonction)"
  - "mbstrlen_l (fonction)"
  - "longueur de chaîne, obtenir"
  - "chaînes (C++), obtenir la longueur"
  - "strlen (fonction)"
  - "tcslen (fonction)"
  - "wcslen (fonction)"
ms.assetid: 16462f2a-1e0f-4eb3-be55-bf1c83f374c2
caps.latest.revision: 32
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la longueur d'une chaîne en utilisant les paramètres régionaux actifs ou des paramètres régionaux spécifiés.  Des versions plus sécurisées de ces fonctions sont disponibles ; voir [strnlen, strnlen\_s, wcsnlen, wcsnlen\_s, \_mbsnlen, \_mbsnlen\_l, \_mbstrnlen, \_mbstrnlen\_l](../../c-runtime-library/reference/strnlen-strnlen-s.md).  
  
> [!IMPORTANT]
>  Les fonctions `_mbslen`, `_mbslen_l`, `_mbstrlen` et `_mbstrlen_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
size_t strlen(    const char *str ); size_t wcslen(    const wchar_t *str  ); size_t _mbslen(    const unsigned char *str  ); size_t _mbslen_l(    const unsigned char *str,    _locale_t locale ); size_t _mbstrlen(    const char *str ); size_t _mbstrlen_l(    const char *str,    _locale_t locale );  
```  
  
#### Paramètres  
 `str`  
 Chaîne se terminant par null.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne le nombre de caractères contenus dans `str`, à l'exclusion du `NULL` terminal.  Aucune valeur de retour n'est réservée pour indiquer une erreur, sauf pour `_mbstrlen` et `_mbstrlen_l`, qui retournent `((size_t)(-1))` si la chaîne contient un caractère multioctets non valide.  
  
## Notes  
 `strlen` interprète la chaîne comme une chaîne de caractères codés sur un octet ; sa valeur de retour est donc toujours égale au nombre d'octets, même si la chaîne contient des caractères multioctets.  `wcslen` est une version à caractères larges de `strlen` ; l'argument de `wcslen` est une chaîne de caractères larges et le nombre de caractères s'entend en caractères larges \(codés sur deux octets\).  Sinon, `wcslen` et `strlen` se comportent de la même façon.  
  
 **Remarque relative à la sécurité** Ces fonctions sont exposées à une menace potentielle liée à un problème de dépassement de mémoire tampon.  Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée.  Pour plus d'informations, voir [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcslen`|`strlen`|`strlen`|`wcslen`|  
|`_tcsclen`|`strlen`|`_mbslen`|`wcslen`|  
|`_tcsclen_l`|`strlen`|`_mbslen_l`|`wcslen`|  
  
 Les fonctions `_mbslen` et `_mbslen_l` retournent le nombre de caractères multioctets contenus dans une chaîne de caractères multioctets, mais elles ne sont pas soumises au test de validité des caractères multioctets.  `_mbstrlen` et `_mbstrlen_l` testent la validité des caractères multioctets et reconnaissent les séquences de caractères multioctets.  Si la chaîne passée à `_mbstrlen` ou `_mbstrlen_l` contient un caractère multioctets non valide pour la page de code, la fonction retourne \-1 et affecte à `errno` la valeur `EILSEQ`.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, voir [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strlen`|\<string.h\>|  
|`wcslen`|\<string.h\> ou \<wchar.h\>|  
|`_mbslen`, `_mbslen_l`|\<mbstring.h\>|  
|`_mbstrlen`, `_mbstrlen_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strlen.c  
// Determine the length of a string. For the multi-byte character  
// example to work correctly, the Japanese language support for  
// non-Unicode programs must be enabled by the operating system.  
  
#include <string.h>  
#include <locale.h>  
  
int main()  
{  
   char* str1 = "Count.";  
   wchar_t* wstr1 = L"Count.";  
   char * mbstr1;  
   char * locale_string;  
  
   // strlen gives the length of single-byte character string  
   printf("Length of '%s' : %d\n", str1, strlen(str1) );  
  
   // wstrlen gives the length of a wide character string  
   wprintf(L"Length of '%s' : %d\n", wstr1, wcslen(wstr1) );  
  
   // A multibyte string: [A] [B] [C] [katakana A] [D] [\0]  
   // in Code Page 932. For this example to work correctly,  
   // the Japanese language support must be enabled by the  
   // operating system.  
   mbstr1 = "ABC" "\x83\x40" "D";  
  
   locale_string = setlocale(LC_CTYPE, "Japanese_Japan");  
  
   if (locale_string == NULL)  
   {  
      printf("Japanese locale not enabled. Exiting.\n");  
      exit(1);  
   }  
   else  
   {  
      printf("Locale set to %s\n", locale_string);  
   }  
  
   // _mbslen will recognize the Japanese multibyte character if the  
   // current locale used by the operating system is Japanese  
   printf("Length of '%s' : %d\n", mbstr1, _mbslen(mbstr1) );  
  
   // _mbstrlen will recognize the Japanese multibyte character  
   // since the CRT locale is set to Japanese even if the OS locale  
   // isnot.   
   printf("Length of '%s' : %d\n", mbstr1, _mbstrlen(mbstr1) );  
   printf("Bytes in '%s' : %d\n", mbstr1, strlen(mbstr1) );     
  
}  
```  
  
  **Longueur de 'Count'. : 6**  
**Longueur de 'Count'. : 6**  
**Longueur de 'ABCァD' : 5**  
**Longueur de 'ABCァD' : 5**  
**Octets dans 'ABCァD' : 6**   
## Équivalent .NET Framework  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)