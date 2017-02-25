---
title: "_mm_cvttss_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvttss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_cvttss_si64x, intrinsèque"
  - "cvttss2si, instruction"
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_cvttss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Effectue la version étendue par x64 du converti avec le nombre à virgule flottante simple précision de troncation à l'instruction d'entiers 64 bits \(`cvttss2si`\).  
  
## Syntaxe  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### Paramètres  
 \[in\] `value`  
 Une structure d' `__m128` qui contiennent des valeurs à virgule flottante simple précision.  
  
## Valeur de retour  
 le résultat de la conversion de la première valeur à virgule flottante à un entier 64 bits.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 L'intrinsèque diffère d' `_mm_cvtss_si64x` uniquement dans la mesure où les conversions inexactes sont tronquées à zéro.  Comme la structure d' `__m128` représente un registre XMM, les instructions générées entre des données à partir d'un registre XMM dans la mémoire système.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_m128](../cpp/m128.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)