---
title: "_atoi64, _atoi64_l, _wtoi64, _wtoi64_l | Microsoft Docs"
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
  - "_atoi64_l"
  - "_wtoi64"
  - "_atoi64"
  - "_wtoi64_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_atoi64"
  - "_tstoi64"
  - "_ttoi64"
  - "wtoi64"
  - "_tstoi64_l"
  - "atoi64"
  - "_wtoi64_l"
  - "_wtoi64"
  - "wtoi64_l"
  - "_atoi64_l"
  - "atoi64_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstoi64 (fonction)"
  - "wtoi64 (fonction)"
  - "atoi64_l (fonction)"
  - "_ttoi64 (fonction)"
  - "conversion de chaînes, en entiers"
  - "wtoi64_l (fonction)"
  - "atoi64 (fonction)"
  - "_tstoi64 (fonction)"
  - "_atoi64_l (fonction)"
  - "_wtoi64_l (fonction)"
  - "ttoi64 (fonction)"
  - "_wtoi64 (fonction)"
  - "_atoi64 (fonction)"
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _atoi64, _atoi64_l, _wtoi64, _wtoi64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne de carractères en entier 64 bits.  
  
## Syntaxe  
  
```  
__int64 _atoi64(  
   const char *str   
);  
__int64 _wtoi64(  
   const wchar_t *str   
);  
__int64 _atoi64_l(  
   const char *str,  
   _locale_t locale  
);  
__int64 _wtoi64_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `str`  
 Chaîne à convertir.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Chaque fonction retourne la valeur `__int64` qui est produite lors de l'interprétation des caractères d'entrée comme des nombres.  La valeur retournée est 0 pour `_atoi64` si l'entrée ne peut pas être convertie en une valeur du même type.  
  
 Dans le cas d'un dépassement de capacité pour de grandes valeurs intégrales positives, `_atoi64` retourne `I64_MAX` et `I64_MIN` dans le cas d'un dépassement de capacité à de grandes valeurs intégrales négatives.  
  
 Dans tous les cas hors limites, `errno` a la valeur `ERANGE`.  Si le paramètre qui est passé est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent 0.  
  
## Notes  
 Ces fonctions convertissent une chaîne de caractères en une valeur entière 64\-bits.  
  
 La chaîne d'entrée est une séquence de caractères qui peuvent être interprétés comme une valeur numérique du type spécifié.  La fonction cesse de lire la chaîne au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Ce caractère peut être le caractère null \('\\0' ou L'\\0'\) qui termine la chaîne.  
  
 L'argument `str` de `_atoi64` a la forme suivante :  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 Un `whitespace` se compose d'espaces ou de caractères de tabulation, qui sont ignorés ; un `sign` est soit plus \(\+\) soit moins \(–\) ; et les `digits` se composent d'un ou de plusieurs chiffres.  
  
 `_wtoi64` équivaut à `_atoi64` mais prend comme paramètre une chaîne à caractères larges.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## Configuration requise  
  
|Routines|En\-tête requis|  
|--------------|---------------------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h\>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
## Exemple  
 Ce programme montre comment les nombres stockés sous la forme de chaines peuvent etre convertis en des valeurs numériques en utilisant les fonctions `_atoi64`.  
  
```  
// crt_atoi64.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the _atoi64 functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    __int64 value = 0;  
  
    // An example of the _atoi64 function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Fonction: \_atoi64\( "  \-2309 " \) \= \-2309**  
**Function: \_atoi64\( "314127.64" \) \= 314127**  
**Function: \_atoi64\( "3336402735171707160320" \) \= \-1**  
**Un cas de dépassement de capacité s'est produit.**   
## Équivalent .NET Framework  
  
-   [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
-   [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)