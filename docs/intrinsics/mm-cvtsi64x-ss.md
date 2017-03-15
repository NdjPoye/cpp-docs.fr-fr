---
title: "_mm_cvtsi64x_ss | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_cvtsi64x_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cvtsi2ss, instruction"
  - "_mm_cvtsi64x_ss, intrinsèque"
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _mm_cvtsi64x_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 génère la version étendue par [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] de l'entier 64 bits de converti à l'instruction scalaire de valeur à virgule flottante simple précision \(`cvtsi2ss`\).  
  
## Syntaxe  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### Paramètres  
 \[in\] `a`  
 Une structure d' `__m128` contenant quatre valeurs à virgule flottante simple précision.  
  
 \[in\] `b`  
 Entier 64 bits à convertir une valeur à virgule flottante.  
  
## Valeur de retour  
 une structure d' `__m128` dont la première valeur à virgule flottante est le résultat de la conversion.  Les trois autres valeurs sont copiées inchangé d' `a`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_cvtsi64x_ss`|x64|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 La structure d' `__m128` représente un registre XMM, cette intrinsèque permet la valeur `b` de la mémoire système à entrer dans un registre XMM.  
  
 Cette routine est uniquement disponible sous forme intrinsèque.  
  
## Exemple  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
  **54.000000 0.000000 0.000000 0.000000**   
## détail de FIN Microsoft  
  
## Voir aussi  
 [\_\_m128](../cpp/m128.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)