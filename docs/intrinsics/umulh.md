---
title: "__umulh | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__umulh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__umulh, intrinsèque"
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __umulh
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Retourner les 64 bits de poids fort du produit de deux entiers non signés 64 bits.  
  
## Syntaxe  
  
```  
unsigned __int64 __umulh(     unsigned __int64 a,     unsigned __int64 b  );  
```  
  
#### Paramètres  
 \[in\] `a`  
 Premier nombre à multiplier.  
  
 \[in\] `b`  
 Second nombre à multiplier.  
  
## Valeur de retour  
 64 bits de poids fort du résultat 128 bits de la multiplication.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__umulh`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## Exemple  
  
```  
// umulh.cpp  
// processor: X64  
#include <cstdio>  
#include <intrin.h>  
  
int main()  
{  
    unsigned __int64 i = 0x10;  
    unsigned __int64 j = 0xFEDCBA9876543210;  
    unsigned __int64 k = i * j; // k has the low 64 bits  
                                // of the product.  
    unsigned __int64 result;  
    result = __umulh(i, j); // result has the high 64 bits  
                            // of the product.  
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);  
    return 0;  
}  
```  
  
  **0x10 \* 0xfedcba9876543210 \= 0xfedcba98765432100**    
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)