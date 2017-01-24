---
title: "atoi, _atoi_l, _wtoi, _wtoi_l | Microsoft Docs"
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
  - "_wtoi"
  - "_wtoi_l"
  - "atoi"
  - "_atoi_l"
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
  - "_tstoi"
  - "_wtoi"
  - "_ttoi"
  - "atoi"
  - "_atoi_l"
  - "_wtoi_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_atoi_l (fonction)"
  - "ttoi (fonction)"
  - "atoi_l (fonction)"
  - "conversion de chaînes, en entiers"
  - "_wtoi (fonction)"
  - "wtoi_l (fonction)"
  - "tstoi (fonction)"
  - "_ttoi (fonction)"
  - "_tstoi (fonction)"
  - "_wtoi_l (fonction)"
  - "atoi (fonction)"
  - "wtoi (fonction)"
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atoi, _atoi_l, _wtoi, _wtoi_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en entier.  
  
## Syntaxe  
  
```  
int atoi(  
   const char *str   
);  
int _wtoi(  
   const wchar_t *str   
);  
int _atoi_l(  
   const char *str,  
   _locale_t locale  
);  
int _wtoi_l(  
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
 Chaque fonction retourne la valeur `int` qui est produite lors de l'interprétation des caractères d'entrée comme des nombres.  La valeur de retour est 0 pour `atoi` et `_wtoi`, si l'entrée ne peut pas être convertie en une valeur de ce type.  
  
 Dans le cas d'un dépassement de capacité avec de grandes valeurs intégrales négatives, `LONG_MIN` est retourné.  `atoi` et `_wtoi` retournent `INT_MAX` et `INT_MIN` dans ces conditions.  Dans tous les cas hors limites, `errno` a la valeur `ERANGE`.  Si le paramètre qui est passé est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent 0.  
  
## Notes  
 Ces fonctions convertissent une chaîne de caractères en une valeur entière \(`atoi` et `_wtoi`\).  La chaîne d'entrée est une séquence de caractères qui peuvent être interprétés comme une valeur numérique du type spécifié.  La fonction cesse de lire la chaîne au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Ce caractère peut être le caractère null \('\\0' ou L'\\0'\) qui termine la chaîne.  
  
 L'argument `str` de `atoi` `` et `_wtoi` a la forme suivante:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 Un `whitespace` se compose d'espaces ou de caractères de tabulation, qui sont ignorés ; un `sign` est soit plus \(\+\) soit moins \(–\) ; et les `digits` se composent d'un ou de plusieurs chiffres.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tstoi`|`atoi`|`atoi`|`_wtoi`|  
|`_ttoi`|`atoi`|`atoi`|`_wtoi`|  
  
## Configuration requise  
  
|Routines|En\-tête requis|  
|--------------|---------------------|  
|`atoi`|\<stdlib.h\>|  
|`_atoi_l`, `_wtoi`, `_wtoi_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
## Exemple  
 Ce programme montre comment les nombres stockés sous la forme de chaines peuvent etre convertis en des valeurs numériques en utilisant les fonctions `atoi`.  
  
```  
// crt_atoi.c  
// This program shows how numbers   
// stored as strings can be converted to  
// numeric values using the atoi functions.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    int     value = 0;  
  
    // An example of the atoi function.  
    str = "  -2309 ";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function.  
    str = "31412764";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function   
    // with an overflow condition occuring.  
    str = "3336402735171707160320";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Fonction: atoi\( " \-2309 " \) \= \-2309**  
**Fonction: atoi\( "31412764" \) \= 31412764**  
**Fonction: atoi\( "3336402735171707160320" \) \= 2147483647**  
**Un cas de dépassement de capacité s'est produit.**   
## Équivalent .NET Framework  
  
-   [System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)  
  
-   [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)