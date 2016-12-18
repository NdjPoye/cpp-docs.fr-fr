---
title: "atoll, _atoll_l, _wtoll, _wtoll_l | Microsoft Docs"
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
  - "_wtoll"
  - "_atoll_l"
  - "_wtoll_l"
  - "atoll"
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
  - "_tstoll_l"
  - "_wtoll"
  - "_atoll_l"
  - "_ttoll"
  - "_tstoll"
  - "_wtoll_l"
  - "atoll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_atoll_l (fonction)"
  - "_wtoll (fonction)"
  - "_wtoll_l (fonction)"
  - "atoll (fonction)"
ms.assetid: 5e85fcac-b351-4882-bff2-6e7c469b7fa8
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atoll, _atoll_l, _wtoll, _wtoll_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une chaîne en entier `long long`.  
  
## Syntaxe  
  
```  
long long atoll(  
   const char *str   
);  
long long _wtoll(  
   const wchar_t *str   
);  
long long _atoll_l(  
   const char *str,  
   _locale_t locale  
);  
long long _wtoll_l(  
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
 Chaque fonction retourne la valeur `long long` qui est produite lors de l'interprétation des caractères d'entrée en tant que nombre.  La valeur de retour de `atoll` est 0 si l'entrée ne peut pas être convertie en une valeur de ce type.  
  
 Pour le dépassement de capacité avec de grandes valeurs intégrales positives, `atoll` retourne `LLONG_MAX`, et pour le dépassement de capacité avec de grandes valeurs intégrales négatives, il retourne `LLONG_MIN`.  
  
 Dans tous les cas hors limites, `errno` a la valeur `ERANGE`.  Si le paramètre qui est passé est `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent 0.  
  
## Notes  
 Ces fonctions convertissent une chaîne de caractères en une valeur entière `long long`.  
  
 La chaîne d'entrée est une séquence de caractères qui peuvent être interprétés comme une valeur numérique du type spécifié.  La fonction cesse de lire la chaîne au premier caractère qu'elle ne peut pas reconnaître comme faisant partie d'un nombre.  Ce caractère peut être le caractère null \('\\0' ou L'\\0'\) qui termine la chaîne.  
  
 L'argument `str` de `atoll` a la forme suivante :  
  
```  
[whitespace] [sign] [digits]  
```  
  
 Un `whitespace` se compose d'espaces ou de caractères de tabulation, qui sont ignorés ; un `sign` est soit plus \(\+\) soit moins \(–\) ; et les `digits` se composent d'un ou de plusieurs chiffres.  
  
 `_wtoll` équivaut à `atoll` mais prend comme paramètre une chaîne à caractères larges.  
  
 Les versions des fonctions qui disposent du suffixe `_l` sont identiques aux versions qui n'en disposent pas, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux actuels.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tstoll`|`atoll`|`atoll`|`_wtoll`|  
|`_tstoll_l`|`_atoll_l`|`_atoll_l`|`_wtoll_l`|  
|`_ttoll`|`_atoll`|`_atoll`|`_wtoll`|  
  
## Configuration requise  
  
|Routines|En\-tête requis|  
|--------------|---------------------|  
|`atoll`, `_atoll_l`|\<stdlib.h\>|  
|`_wtoll`, `_wtoll_l`|\<stdlib.h\> ou \<wchar.h\>|  
  
## Exemple  
 Ce programme montre comment utiliser les fonctions `atoll` pour convertir des nombres stockés sous forme de chaînes en valeurs numériques.  
  
```  
// crt_atoll.c  
// Build with: cl /W4 /Tc crt_atoll.c  
// This program shows how to use the atoll   
// functions to convert numbers stored as   
// strings to numeric values.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main(void)  
{  
    char *str = NULL;  
    long long value = 0;  
  
    // An example of the atoll function  
    // with leading and trailing white spaces.  
    str = "  -27182818284 ";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
  
    // Another example of the atoll function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
  
    // Another example of the atoll function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atoll(str);  
    printf("Function: atoll(\"%s\") = %lld\n", str, value);  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **Function: atoll\("  \-27182818284 "\) \= \-27182818284**  
**Function: atoll\("314127.64"\) \= 314127**  
**Function: atoll\("3336402735171707160320"\) \= 9223372036854775807**  
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