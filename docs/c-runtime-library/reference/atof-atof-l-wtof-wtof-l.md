---
title: "atof, _atof_l, _wtof, _wtof_l | Microsoft Docs"
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
  - "_wtof_l"
  - "atof"
  - "_atof_l"
  - "_wtof"
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
  - "_tstof"
  - "_ttof"
  - "atof"
  - "stdlib/atof"
  - "math/atof"
  - "_atof_l"
  - "stdlib/_atof_l"
  - "math/_atof_l"
  - "_wtof"
  - "corecrt_wstdlib/_wtof"
  - "_wtof_l"
  - "corecrt_wstdlib/_wtof_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstof, fonction"
  - "atof_l, fonction"
  - "_atof_l, fonction"
  - "atof, fonction"
  - "_tstof, fonction"
  - "_ttof, fonction"
  - "wtof, fonction"
  - "_wtof_l, fonction"
  - "ttof, fonction"
  - "wtof_l, fonction"
  - "_wtof, fonction"
  - "conversion de chaînes, en valeurs à virgule flottante"
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
caps.latest.revision: 26
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atof, _atof_l, _wtof, _wtof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertir une chaîne en double.  
  
## Syntaxe  
  
```  
double atof(  
   const char *str   
);  
double _atof_l(  
   const char *str,  
   _locale_t locale  
);  
double _wtof(  
   const wchar_t *str   
);  
double _wtof_l(  
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
 Chaque fonction retourne la valeur `double` qui est produite lors de l'interprétation des caractères d'entrée comme des nombres.  La valeur de retour est 0.0 si l'entrée ne peut pas être convertie en une valeur de ce type.  
  
 Dans tous les cas hors limites, errno est défini à la valeur`ERANGE`.  Si le paramètre qui est passé est `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent 0.  
  
## Notes  
 Ces fonctions convertissent une chaîne de caractères en une valeur double précision, valeur à virgule flottante.  
  
 La chaîne d'entrée est une séquence de caractères qui peuvent être interprétés comme une valeur numérique du type spécifié.  La fonction cesse de lire la chaîne au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Ce caractère peut être le caractère null \('\\0' ou L'\\0'\) qui termine la chaîne.  
  
 L'argument `str` de `atof`et `_wtof`a la forme suivante:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E` }\[`sign`\]`digits`\]  
  
 Un `whitespace` se compose d'un espace ou de caractères de tabulation, qui sont ignorés ; `sign` est soit plus \(\+\) soit moins \(–\) ; et les `digits` se composent d'un ou de plusieurs chiffres.  Si aucun chiffre n'apparaît avant la virgule, au moins un doit apparaître après la virgule.  Les nombres décimaux peuvent être suivis d'un exposant, qui comprend une lettre préliminaire \(`d`, `D`, `e` ou `E`\) et éventuellement un entier décimal signé.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tstof`|`atof`|`atof`|`_wtof`|  
|`_ttof`|`atof`|`atof`|`_wtof`|  
  
## Configuration requise  
  
|Routine\(s\)|En\-tête requis|  
|------------------|---------------------|  
|`atof`|\<stdlib.h\> ou \<math.h\>|  
|`_atof_l`|\<stdlib.h\> ou \<math.h\>|  
|`_wtof`, `_wtof_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
## Exemple  
 Ce programme montre comment les nombres stockés sous la forme de chaines peuvent etre convertis en des valeurs numériques en utilisant la fonction `atof`.  
  
```  
// crt_atof.c  
//  
// This program shows how numbers stored as   
// strings can be converted to numeric  
// values using the atof function.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    double  value = 0;  
  
    // An example of the atof function  
    // using leading and training spaces.  
    str = "  3336402735171707160320 ";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // Another example of the atof function  
    // using the 'd' exponential formatting keyword.  
    str = "3.1412764583d210";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // An example of the atof function  
    // using the 'e' exponential formatting keyword.  
    str = "  -2309.12E-15";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
}  
```  
  
  **Fonction : atof \(« 3336402735171707160320 "\) \= 3.336403e\+021**  
**Fonction : atof \(« 3.1412764583d210 »\) \= 3.141276e\+210**  
**Fonction : atof \(« \-2309.12E\-15 »\) \= \-2.309120e\-012**   
## Équivalent .NET Framework  
  
-   [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
-   [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [\_atodbl, \_atodbl\_l, \_atoldbl, \_atoldbl\_l, \_atoflt, \_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)