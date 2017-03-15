---
title: "wctrans | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wctrans"
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
  - "wctrans"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codes de caractères, wctrans"
  - "caractères, codes"
  - "caractères, convertir"
  - "wctrans (fonction)"
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# wctrans
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine un mapping à partir d'un ensemble de codes de caractères à un autre.  
  
## Syntaxe  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### Paramètres  
 `property`  
 Chaîne qui spécifie l'une des transformations valides.  
  
## Valeur de retour  
 Si la catégorie `LC_CTYPE` des paramètres régionaux actuels ne définit pas de mapping dont le nom correspond à la catégorie chaîne de caractères `property`, la fonction retourne zéro.  Sinon, elle retourne une valeur non nulle appropriée à utiliser comme deuxième argument pour un appel suivant à [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## Notes  
 Cette fonction détermine un mapping à partir d'un ensemble de codes de caractères à un autre.  
  
 Les paires suivantes d'appels ont le même comportement dans les paramètres régionaux, mais il est possible de définir des mappings supplémentaires même dans les paramètres régionaux « c »:  
  
|Fonction|Identique à .|  
|--------------|-------------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`wctrans`|\<wctype.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
  **97**  
**1**  
**0**  
**65**   
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)