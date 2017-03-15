---
title: "_umul128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__umul128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__umul128 intrinsic"
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _umul128
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Multiplie deux entiers non signés 64 bits passés comme les deux premiers arguments, place les 64 bits de poids fort du produit dans l'entier non signé 64 bits vers lequel pointe `HighProduct` et retourne les 64 bits de poids faible du produit.  
  
## Syntaxe  
  
```  
unsigned __int64 _umul128(     unsigned __int64 Multiplier,     unsigned __int64 Multiplicand,     unsigned __int64 *HighProduct  );  
```  
  
#### Paramètres  
 \[in\] `Multiplier`  
 Premier entier de 64 bits à multiplier.  
  
 \[in\] `Multiplicand`  
 Second entier de 64 bits à multiplier.  
  
 \[out\] `HighProduct`  
 64 bits de poids fort du produit.  
  
## Valeur de retour  
 64 bits de poids faible du produit.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_umul128`|ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
  
## Exemple  
  
```  
// umul128.c  
// processor: IPF, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_umul128)  
  
int main()  
{  
    unsigned __int64 a = 0x0fffffffffffffffI64;  
    unsigned __int64 b = 0xf0000000I64;  
    unsigned __int64 c, d;  
  
    d = _umul128(a, b, &c);  
  
    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);  
}  
```  
  
  **0xfffffffffffffff \* 0xf0000000 \= 0xeffffffffffffff10000000**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)