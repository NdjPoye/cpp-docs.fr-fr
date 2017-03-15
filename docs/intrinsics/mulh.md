---
title: "__mulh | Microsoft Docs"
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
  - "__mulh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__mulh, intrinsèque"
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __mulh
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Retourne les bits de grande 64 du produit de deux entiers signés 64 bits.  
  
## Syntaxe  
  
```  
__int64 __mulh(   
   __int64 a,   
   __int64 b   
);  
```  
  
#### Paramètres  
 \[in\] `a`  
 Premier nombre à multiplier.  
  
 \[in\] `b`  
 Second nombre à multiplier.  
  
## Valeur de retour  
 Les bits de grande 64 du résultat 128 bits de la multiplication.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__mulh`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// mulh.cpp  
// processor: x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic (__mulh)  
  
int main()  
{  
    __int64 a = 0x0fffffffffffffffI64;  
    __int64 b = 0xf0000000I64;  
  
    __int64 result = __mulh(a, b); // the high 64 bits  
    __int64 result2 = a * b; // the low 64 bits  
  
    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",  
             a, b, result, result2);  
}  
```  
  
  **0xfffffffffffffff \* 0xf0000000 \= 0xeffffffffffffff10000000**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)