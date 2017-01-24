---
title: "_mm_stream_ss | Microsoft Docs"
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
  - "_mm_stream_ss"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "movntss, instruction"
  - "_mm_stream_ss, intrinsèque"
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_stream_ss
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Écrit des données 32 bits à un emplacement mémoire sans polluer les caches.  
  
## Syntaxe  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### Paramètres  
 \[out\] `Dest`  
 Pointeur vers l'emplacement où les données sources sont écrites.  
  
 \[in\] `Source`  
 Un nombre de bits qui contient la valeur de `float` à écrire dans ses bits du bas 32.  
  
## Valeur de retour  
 Aucun  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d' `movntss`.  Pour déterminer la prise en charge matérielle pour cette instruction, appelez l'intrinsèque de `__cpuid` avec `InfoType=0x80000001`et le bit de contrôle 6 d' `CPUInfo[2] (ECX)`.  Ce bit est égal à 1 lorsque l'instruction est prise en charge, sinon il est égal à 0.  
  
 Si vous exécutez le code qui utilise l'intrinsèque de `_mm_stream_ss` sur le matériel qui ne prend pas en charge l'instruction d' `movntss` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
  
```  
  
  **f \[0\] \= \-1, f \[1\] \= \-2**  
**f \[2\] \= \-3, f \[3\] \= 3**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [\_mm\_stream\_sd](../intrinsics/mm-stream-sd.md)   
 [\_mm\_stream\_ps](http://msdn.microsoft.com/fr-fr/f7af2f19-c0d4-43c6-b5f6-a658d2b1d869)   
 [\_mm\_store\_ss](http://msdn.microsoft.com/fr-fr/dfeeea35-8faf-4f54-8a9e-6723e226fb08)   
 [\_mm\_sfence](http://msdn.microsoft.com/fr-fr/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/fr-fr/8f03493a-d5f5-4457-892e-0b6540494872)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)