---
title: "strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wcsnlen"
  - "strnlen_s"
  - "_mbstrnlen"
  - "_mbsnlen_l"
  - "_mbstrnlen_l"
  - "strnlen"
  - "wcsnlen_s"
  - "_mbsnlen"
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
  - "wcsnlen"
  - "strnlen_s"
  - "_mbsnlen"
  - "_mbsnlen_l"
  - "_tcsnlen"
  - "_tcscnlen"
  - "_mbstrnlen_l"
  - "wcsnlen_s"
  - "_mbstrnlen"
  - "strnlen"
  - "_tcscnlen_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnlen (fonction)"
  - "_mbsnlen_l (fonction)"
  - "_mbstrnlen (fonction)"
  - "_mbstrnlen_l (fonction)"
  - "_tcscnlen (fonction)"
  - "_tcscnlen_l (fonction)"
  - "_tcsnlen (fonction)"
  - "longueurs, chaînes"
  - "mbsnlen (fonction)"
  - "mbsnlen_l (fonction)"
  - "mbstrnlen (fonction)"
  - "mbstrnlen_l (fonction)"
  - "longueur de chaîne"
  - "strnlen (fonction)"
  - "strnlen_l (fonction)"
  - "strnlen_s (fonction)"
  - "wcsnlen (fonction)"
  - "wcsnlen_l (fonction)"
  - "wcsnlen_s (fonction)"
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
caps.latest.revision: 35
caps.handback.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient la longueur d'une chaîne en utilisant les paramètres régionaux actuels ou ceux qui ont été passés.  Il s'agit de versions plus sécurisées de [strlen, wcslen, \_mbslen, \_mbslen\_l, \_mbstrlen, \_mbstrlen\_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).  
  
> [!IMPORTANT]
>  `_mbsnlen`, `_mbsnlen_l`, `_mbstrnlen` et `_mbstrnlen_l` ne peuvent pas être utilisés dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
size_t strnlen(  
   const char *str,  
   size_t numberOfElements   
);  
size_t strnlen_s(  
   const char *str,  
   size_t numberOfElements   
);  
size_t wcsnlen(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t wcsnlen_s(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen(  
   const unsigned char *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen_l(  
   const unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
size_t _mbstrnlen(  
   const char *str,  
   size_t numberOfElements  
);  
size_t _mbstrnlen_l(  
   const char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne terminée par un caractère Null.  
  
 `numberOfElements`  
 Taille de la mémoire tampon de chaîne.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Ces fonctions retournent le nombre de caractères dans la chaîne, sans le caractère Null de fin.  En l'absence de marque de fin Null dans les `numberOfElements` premiers octets de la chaîne \(ou caractères larges pour `wcsnlen`\), `numberOfElements` est retourné pour indiquer la condition d'erreur ; les chaînes terminées par un caractère Null ont des longueurs qui sont strictement inférieures à `numberOfElements`.  
  
 `_mbstrnlen` et `_mbstrnlen_l` retournent \-1 si la chaîne contient un caractère multioctet non valide.  
  
## Notes  
  
> [!NOTE]
>  `strnlen` ne remplace pas `strlen` ; `strnlen` est destiné à être utilisé uniquement pour calculer la taille des données entrantes non fiables dans une mémoire tampon de taille connue, par exemple un paquet réseau.  `strnlen` calcule la longueur mais ne continue pas après la fin de la mémoire tampon si la chaîne n'est pas terminée.  Pour d'autres situations, utilisez `strlen`.  \(Également applicable à `wcsnlen`, `_mbsnlen` et `_mbstrnlen`.\)  
  
 Chacune de ces fonctions retourne le nombre de caractères dans `str`, sans le caractère Null de fin.  Toutefois, `strnlen` et `strnlen_s` interprètent la chaîne comme une chaîne de caractères composée d'un unique octet et la valeur de retour est donc toujours égale au nombre d'octets, même si la chaîne contient des caractères multioctets.  `wcsnlen` et `wcsnlen_s` sont des versions à caractères larges de `strnlen` et `strnlen_s` respectivement ; les arguments pour `wcsnlen` et `wcsnlen_s` sont des chaînes à caractères larges et le nombre de caractères est établi en unités à caractères larges.  Sinon, `wcsnlen` et `strnlen` se comportent de la même façon, comme `strnlen_s` et `wcsnlen_s`.  
  
 `strnlen`, `wcsnlen,` et `_mbsnlen` ne valident pas leurs paramètres.  Si `str` a la valeur `NULL`, une violation d'accès se produit.  
  
 `strnlen_s` et `wcsnlen_s` valident leurs paramètres.  Si `str` a la valeur `NULL`, les fonctions retournent 0.  
  
 `_mbstrnlen` valide également ses paramètres.  Si `str` a la valeur `NULL` ou si `numberOfElements` est supérieur à `INT_MAX`, `_mbstrnlen` génère une exception de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `_mbstrnlen` affecte à `errno` la valeur `EINVAL` et retourne \-1.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnlen`|`strnlen`|`strnlen`|`wcsnlen`|  
|`_tcscnlen`|`strnlen`|`_mbsnlen`|`wcsnlen`|  
|`_tcscnlen_l`|`strnlen`|`_mbsnlen_l`|`wcsnlen`|  
  
 `_mbsnlen` et `_mbstrnlen` retournent le nombre de caractères multioctets dans une chaîne de caractères multioctets.  `_mbsnlen` identifie les séquences de caractères multioctets selon la page de codes multioctets actuellement utilisée ou selon les paramètres régionaux passés ; il ne teste pas la validité des caractères multioctets.  `_mbstrnlen` teste la validité des caractères multioctets et identifie les séquences de caractères multioctets.  Si la chaîne transmise à `_mbstrnlen` contient un caractère multioctet non valide, `errno` prend la valeur `EILSEQ`.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sont identiques, excepté que celles qui n'ont pas le suffixe `_l` utilisent les paramètres régionaux actuels pour ce comportement dépendant de ces paramètres, et les versions qui ont le suffixe `_l` utilisent plutôt les paramètres régionaux qui ont été passés.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`strnlen`, `strnlen_s`|\<string.h\>|  
|`wcsnlen`, `wcsnlen_s`|\<string.h\> ou \<wchar.h\>|  
|`_mbsnlen`, `_mbsnlen_l`|\<mbstring.h\>|  
|`_mbstrnlen`, `_mbstrnlen_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_strnlen.c  
  
#include <string.h>  
  
int main()  
{  
   // str1 is 82 characters long. str2 is 159 characters long   
  
   char* str1 = "The length of a string is the number of characters\n"  
               "excluding the terminating null.";  
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"  
                "than the maximum size specified, the maximum size is\n"  
                "returned rather than the actual size of the string.";  
   size_t len;  
   size_t maxsize = 100;  
  
   len = strnlen(str1, maxsize);  
   printf("%s\n Length: %d \n\n", str1, len);  
  
   len = strnlen(str2, maxsize);  
   printf("%s\n Length: %d \n", str2, len);  
}  
```  
  
  **La longueur d'une chaîne correspond au nombre de caractères qu'elle contient**  
**à l'exception du caractère Null de fin.  Longueur : 82**   
**strnlen accepte une taille maximale.  Si la chaîne est plus longue**  
**que la taille maximale spécifiée, la taille maximale est**  
**retournée au lieu de la taille réelle de la chaîne.  Longueur : 100**    
## Équivalent .NET Framework  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)