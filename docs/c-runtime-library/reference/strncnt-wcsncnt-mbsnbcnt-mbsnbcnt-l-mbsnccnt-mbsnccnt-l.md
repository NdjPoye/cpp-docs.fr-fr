---
title: "_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbcnt_l"
  - "_mbsnccnt"
  - "_wcsncnt"
  - "_strncnt"
  - "_mbsnccnt_l"
  - "_mbsnbcnt"
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
  - "_mbsnbcnt"
  - "wcsncnt"
  - "_tcsnbcnt"
  - "_mbsnccnt"
  - "_ftcsnbcnt"
  - "mbsnbcnt"
  - "strncnt"
  - "mbsnbcnt_l"
  - "mbsnccnt_l"
  - "mbsnccnt"
  - "_strncnt"
  - "_wcsncnt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbcnt (fonction)"
  - "_mbsnbcnt_l (fonction)"
  - "_mbsnccnt (fonction)"
  - "_mbsnccnt_l (fonction)"
  - "_strncnt (fonction)"
  - "_tcsnbcnt (fonction)"
  - "_wcsncnt (fonction)"
  - "mbsnbcnt (fonction)"
  - "mbsnbcnt_l (fonction)"
  - "mbsnccnt (fonction)"
  - "mbsnccnt_l (fonction)"
  - "strncnt (fonction)"
  - "tcsnbcnt (fonction)"
  - "wcsncnt (fonction)"
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne le nombre de caractères ou d'octets parmi un nombre spécifié de caractères.  
  
> [!IMPORTANT]
>  `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, et `_mbsnccnt_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
size_t _strncnt(  
   const char *str,  
   size_t count  
);  
size_t _wcsncnt(  
   const wchar_t *str,  
   size_t count  
);  
size_t _mbsnbcnt(  
   const unsigned char *str,  
   size_t count   
);  
size_t _mbsnbcnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
size_t _mbsnccnt(  
   const unsigned char *str,  
   size_t count  
);  
size_t _mbsnccnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
  
```  
  
#### Paramètres  
 `str`  
 Chaîne à examiner.  
  
 `count`  
 Nombre de caractères ou octets à examiner dans `str`.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 `_mbsnbcnt` et `_mbsnbcnt_l` retournent le nombre d'octets trouvés dans le premier `count` des caractères multioctets de `str`.  `_mbsnccnt` et `_mbsnccnt_l` retournent le nombre de caractères trouvés dans le premier `count` des bits de `str`.  Si un caractère Null est trouvé avant la fin de l'examen de `str`, elles retournent le nombre d'octets ou de caractères avant le caractère Null.  Si `str` se compose de moins de caractères ou d'octets que `count`, elles retournent le nombre de caractères ou d'octets dans la chaîne.  Si `count` est inférieur à zéro, elles retournent 0.  Dans les versions antérieures, ces fonctions ont eu la valeur de retour de type `int` plutôt que `size_t`.  
  
 `_strncnt` retourne le nombre de caractères dans les `count` premiers octets de la chaîne codée sur un octet `str`.  `_wcsncnt` retourne le nombre de caractères dans les `count` premiers caractères larges de la chaîne à caractères larges `str`.  
  
## Notes  
 `_mbsnbcnt` et `_mbsnbcnt_l` retournent le nombre d'octets trouvés dans les  `count` premiers des caractères multioctets de `str`.  `_mbsnbcnt` et `_mbsnbcnt_l` remplacent `mtob` et doivent être utilisés à la place d'`mtob`.  
  
 `_mbsnccnt` et `_mbsnccnt_l` comptent le nombre de caractères trouvés dans les premiers `count` des bits de `str`.  Si `_mbsnccnt` et `_mbsnccnt_l` rencontrent null dans le deuxième octet d'un caractère codé sur deux octets, le premier octet est également pris Null et n'est pas inclus dans la valeur retournée de nombre.  `_mbsnccnt` et `_mbsnccnt_l` remplacent `btom` et doivent être utilisés à la place d'`btom`.  
  
 Si `str` est un pointeur null ou `count` est nul, ces fonctions appelleront le gestionnaire de paramètres non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md), `errno` est défini à `EINVAL`, et la fonction retourne 0.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|-------------|-------------------------------------|-------------------|----------------------|  
|`_tcsnbcnt`|`_strncnt`|`_mbsnbcnt`|`_wcsncnt`|  
|`_tcsnccnt`|`_strncnt`|`_mbsnbcnt`|`n/a`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnbcnt`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnccnt`|  
|`n/a`|`n/a`|`_mbsnbcnt_l`|`_mbsnccnt_l`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbsnbcnt`|\<mbstring.h\>|  
|`_mbsnbcnt_l`|\<mbstring.h\>|  
|`_mbsnccnt`|\<mbstring.h\>|  
|`_mbsnccnt_l`|\<mbstring.h\>|  
|`_strncnt`|\<tchar.h\>|  
|`_wcsncnt`|\<tchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_mbsnbcnt.c  
  
#include  <mbstring.h>  
#include  <stdio.h>  
  
int main( void )  
{  
   unsigned char str[] = "This is a multibyte-character string.";  
   unsigned int char_count, byte_count;  
   char_count = _mbsnccnt( str, 10 );  
   byte_count = _mbsnbcnt( str, 10 );  
   if ( byte_count - char_count )  
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );  
   else  
      printf( "The first 10 characters are single-byte.\n");  
}  
```  
  
## Sortie  
  
```  
The first 10 characters are single-byte.  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)