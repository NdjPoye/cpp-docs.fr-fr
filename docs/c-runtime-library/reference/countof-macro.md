---
title: "_countof Macro | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
apitype: "DLLExport"
f1_keywords: 
  - "_countof"
  - "countof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_countof (macro)"
  - "countof (macro)"
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _countof Macro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le nombre d'éléments dans un tableau alloué de manière statique.  
  
## Syntaxe  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### Paramètres  
 `array`  
 Nom d'un tableau.  
  
## Valeur de retour  
 Nombre d'éléments dans le tableau, exprimé sous la forme `size_t`.  
  
## Notes  
 Assurez\-vous que `array` est bien un tableau et non un pointeur.  En C, `_countof` produit des résultats erronés si `array` est un pointeur.  En C\+\+, `_countof` fait échouer la compilation si `array` est un pointeur.  
  
## Configuration requise  
  
|Macro|En\-tête requis|  
|-----------|---------------------|  
|`_countof`|\<stdlib.h\>|  
  
## Exemple  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
  **sizeof\(arr\) \= 40 bytes**  
**\_countof\(arr\) \= 20 elements**   
## Voir aussi  
 [sizeof, opérateur](../../cpp/sizeof-operator.md)