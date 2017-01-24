---
title: "_bittestandreset, _bittestandreset64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandreset64_cpp"
  - "_bittestandreset"
  - "_bittestandreset_cpp"
  - "_bittestandreset64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bittestandreset intrinsic"
  - "_bittestandreset64 intrinsic"
  - "btr instruction"
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _bittestandreset, _bittestandreset64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Générer l'instruction qui examine le bit `b` de l'adresse `a`, retourne sa valeur actuelle et réinitialise le bit à la valeur 0.  
  
## Syntaxe  
  
```  
unsigned char _bittestandreset(    long *a,    long b ); unsigned char _bittestandreset64(    __int64 *a,    __int64 b );  
```  
  
#### Paramètres  
 \[in, out\] `a`  
 Pointeur vers la mémoire à examiner.  
  
 \[in\] `b`  
 Position du bit à tester.  
  
## Valeur de retour  
 Bit à la position spécifiée.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_bittestandreset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandreset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est disponible uniquement en tant qu'intrinsèque.  
  
## Exemple  
  
```  
// bittestandreset.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <limits.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandreset)  
  
// Check the sign bit and reset to 0 (taking the absolute value)  
// Returns 0 if the number is positive or zero  
// Returns 1 if the number is negative  
unsigned char absolute_value(long* p)  
{  
   const int SIGN_BIT = 31;  
   return _bittestandreset(p, SIGN_BIT);  
}  
  
int main()  
{  
    long i = -112;  
    unsigned char result;  
  
    // Check the sign bit and reset to 0 (taking the absolute value)  
  
    result = absolute_value(&i);  
    if (result == 1)  
        printf_s("The number was negative.\n");     
}  
```  
  
  **Le nombre était négatif.**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)