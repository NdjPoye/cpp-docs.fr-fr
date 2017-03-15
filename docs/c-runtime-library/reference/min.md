---
title: "__min | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__min"
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
  - "__min"
  - "min"
  - "_min"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__min (macro)"
  - "_min (macro)"
  - "min (macro)"
  - "minimum (macro)"
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# __min
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la plus petite des deux valeurs .  
  
## Syntaxe  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### Paramètres  
 `type`  
 Tous les types de données numériques  
  
 `a, b`  
 Valeurs de tout type numérique à comparer.  
  
## Valeur de retour  
 Le plus petit des deux arguments.  
  
## Notes  
 La macro `__min` compare deux valeurs et retourne la valeur la plus petite.  Les arguments peuvent être de n'importe quel type de données numérique, signé ou non signé.  Les arguments et la valeur de retour doivent être du même type.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`__min`|\<stdlib.h\>|  
  
## Exemple  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
  **Le plus grand parmis 10 et 21 est 21**  
**Le plus petit parmis 10 et 21 est 10**   
## Équivalent .NET Framework  
 [System::Math::Min](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_\_max](../../c-runtime-library/reference/max.md)