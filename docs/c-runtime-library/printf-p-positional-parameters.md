---
title: "Param&#232;tres positionnels printf_p | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_printf_p (fonction), paramètres de position"
  - "printf_p (fonction), paramètres de position"
ms.assetid: beb4fd85-a7aa-4665-9085-2c907a5b9ab0
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Param&#232;tres positionnels printf_p
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les paramètres positionnels permettent de spécifier à l'aide d'un nombre l'argument à remplacer dans un champ de chaîne de format.  Voici les fonctions `printf` avec paramètres positionnels disponibles :  
  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)  
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)  
  
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)  
 [\_sprintf\_p, \_sprintf\_p\_l, \_swprintf\_p, \_swprintf\_p\_l](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)  
  
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)  
 [\_cprintf\_p, \_cprintf\_p\_l, \_cwprintf\_p, \_cwprintf\_p\_l](../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)  
  
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)  
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)  
  
 [vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
 [\_vprintf\_p, \_vprintf\_p\_l, \_vwprintf\_p, \_vwprintf\_p\_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)  
  
 [vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)  
 [\_vfprintf\_p, \_vfprintf\_p\_l, \_vfwprintf\_p, \_vfwprintf\_p\_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)  
  
 [vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)  
 [\_vsprintf\_p, \_vsprintf\_p\_l, \_vswprintf\_p, \_vswprintf\_p\_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)  
  
## Spécification des paramètres positionnels  
  
##### Indexation des paramètres  
 Par défaut, les fonctions positionnelles se comportent comme les fonctions non positionnelles, en l'absence de format positionnel.  Les paramètres positionnels sont spécifiés à l'aide du format "`%m$x`", où `m` représente un nombre ordinal indiquant la position du paramètre dans la liste des paramètres, avant la chaîne de format, et où  `x` représente le type de caractère de champ de type spécifié dans la fonction `printf`.  Les paramètres de la liste sont indexés à partir de la valeur 1 pour le premier élément de la liste, et ainsi de suite.  Pour plus d'informations sur les caractères du champ de type, consultez [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md).  
  
 Pour obtenir un exemple de ce comportement :  
  
```  
_printf_p("%1$s %2$s", "November", "10");  
```  
  
 affiche  
  
```  
November 10  
```  
  
 Il n'est pas nécessaire que l'ordre des nombres utilisés corresponde à l'ordre des arguments donné.  Ce qui suit est donc valide :  
  
```  
_printf_p("%2$s %1$s", "November", "10");  
```  
  
 affiche  
  
```  
10 November  
```  
  
 Comme le paramètre peut être utilisé plusieurs fois durant la mise en forme, contrairement aux chaînes de format classiques, la ligne ci\-dessous  
  
```  
_printf_p("%1$d times %1$d is %2$d", 10, 100);  
```  
  
 affiche  
  
```  
10 times 10 is 100  
```  
  
 Toutefois, tous les arguments doivent être utilisés au moins une fois dans la chaîne de format.  
  
 Le nombre maximal de paramètres positionnels autorisés dans une chaîne de format est fourni par `_ARGMAX`.  
  
##### Largeur et précision  
 Quand le symbole \* est utilisé pour spécifier que la largeur ou la précision doit être déterminée à partir d'un argument, la position de la valeur de largeur ou de précision doit se trouver immédiatement après le symbole \*.  Par exemple :  
  
```  
_printf_p("%1$*2$s","Hello", 10);  
```  
  
 ou  
  
```  
_printf_p("%2$*1$s",10, "Hello");  
```  
  
##### Mélange d'arguments positionnels et non positionnels  
 Les paramètres positionnels ne doivent pas être mélangés avec des paramètres non positionnels dans la même chaîne de format.  Toutefois, `printf_p` et les fonctions connexes prennent toujours en charge les paramètres non positionnels dans les chaînes de format qui contiennent des paramètres positionnels.  
  
## Exemple  
  
```  
// positional_args.c  
// Positional arguments allow the specification of the order  
// in which arguments are consumed in a formatting string.  
  
#include <stdio.h>  
  
int main(int argc, char *argv[])  
{  
    int     i = 1,  
            j = 2,  
            k = 3;  
    double  x = 0.1,  
            y = 0.2,  
            z = 0.3;  
    char    *s1 = "abc",  
            *s2 = "def",  
            *s3 = "ghi";  
  
    // If positional arguments are unspecified,  
    // normal input order is used.  
    _printf_p("%d %d %d\n", i, j, k);  
  
    // Positional args are numbers indicating the  
    // argument enclosed in curly braces.  
    _printf_p("%3$d %1$d %2$d\n", i, j, k);  
  
    // The same positional argument may be reused.  
    _printf_p("%1$d %2$d %1$d\n", i, j);  
  
    _printf_p("%1$s %2$s %3$s\n", s1, s2, s3);  
  
    _printf_p("%3$s %1$s %2$s\n", s1, s2, s3);  
}  
```  
  
  **1 2 3**  
**3 1 2**  
**1 2 1**  
**abc def ghi**  
**ghi abc def**   
## Voir aussi  
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)