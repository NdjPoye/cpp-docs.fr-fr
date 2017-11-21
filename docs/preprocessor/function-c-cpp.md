---
title: fonction (C/C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs: C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 956c02d7b7df4998187c82cc1dd1c31f196e68b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="function-cc"></a>function (C/C++)
Spécifie que les appels aux fonctions spécifiées dans la liste d’arguments du pragma sont générés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>Remarques  
 Si vous utilisez la **intrinsèque** pragma (ou /Oi) pour indiquer au compilateur de générer des fonctions intrinsèques (les fonctions intrinsèques sont générées en tant que code inline, pas comme des appels de fonction), vous pouvez utiliser la **fonction** pragma Pour forcer explicitement un appel de fonction. Lorsqu'un pragma function est détecté, il prend effet à la première définition de fonction contenant une fonction intrinsèque spécifiée. L’effet se poursuit jusqu'à la fin du fichier source ou à l’apparence d’un **intrinsèque** pragma spécifiant la même fonction intrinsèque. Le **fonction** pragma peut être utilisé uniquement en dehors d’une fonction, au niveau global.  
  
 Pour les listes des fonctions qui ont des formes intrinsèques, consultez [#pragma intrinsic](../preprocessor/intrinsic.md).  
  
## <a name="example"></a>Exemple  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
```Output  
str is 'Now************'  
str is '!!!!!!!!!!!!!!!'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)