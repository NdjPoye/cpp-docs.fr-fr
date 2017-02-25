---
title: "_mm_cvtss_si64x | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvtss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtss2si, intrinsèque"
  - "_mm_cvtss_si64x, intrinsèque"
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_cvtss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère la version étendue par [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] du nombre à virgule flottante scalaire de simple précision de converti à l'instruction d'entiers 64 bits \(`cvtss2si`\).  
  
## Syntaxe  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### Paramètres  
 \[in\] `value`  
 Une structure d' `__m128` qui contiennent des valeurs à virgule flottante.  
  
## Valeur de retour  
 Entier 64 bits, le résultat de la conversion de la première valeur à virgule flottante en un entier.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Le premier élément de la valeur de structure est converti en un entier et retourné.  Les bits de contrôle d'arrondi dans MXCSR utilisés pour déterminer le comportement d'arrondi.  Le mode d'arrondi par défaut est en rond le plus proche, arrondies pair au chiffre si la partie décimale a 0,5 ans.  Comme la structure d' `__m128` représente un registre XMM, cette intrinsèque prend une valeur à partir de le registre XMM et l'écrit dans la mémoire système.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_m128d](../cpp/m128d.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)