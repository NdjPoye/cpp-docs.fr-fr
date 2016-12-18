---
title: "_mm_stream_sd | Microsoft Docs"
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
  - "_mm_stream_sd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mm_stream_sd, intrinsèque"
  - "movntsd, instruction"
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_stream_sd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Écrit des données 64 bits à un emplacement mémoire sans polluer les caches.  
  
## Syntaxe  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### Paramètres  
 \[out\] `Dest`  
 Pointeur vers l'emplacement où les données sources sont écrites.  
  
 \[in\] `Source`  
 Une valeur 128 bits qui contient la valeur d' `double` à écrire dans ses bits du bas 64.  
  
## Valeur de retour  
 Aucun  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Cette intrinsèque génère des instructions d' `movntsd`.  Pour déterminer la prise en charge matérielle pour cette instruction, appelez l'intrinsèque de `__cpuid` avec `InfoType=0x80000001` et le bit de contrôle 6 d' `CPUInfo[2] (ECX)`.  Ce bit est 1 si le contrôle prend en charge matérielle cette instruction, et 0 sinon.  
  
 Si vous exécutez le code qui utilise l'intrinsèque de `_mm_stream_sd` sur le matériel qui ne prend pas en charge l'instruction d' `movntsd` , les résultats sont imprévisibles.  
  
## Exemple  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
  **d \[0\] \= \-1, d \[1\] \= 1**   
## détail de FIN Microsoft  
 copyright 2007 par Advanced Micro Devices, Inc.  Tous droits réservés.  reproduit avec l'autorisation d'Advanced Micro Devices, Inc.  
  
## Voir aussi  
 [\_mm\_stream\_ss](../intrinsics/mm-stream-ss.md)   
 [\_mm\_store\_sd](http://msdn.microsoft.com/fr-fr/8e672d0d-0a96-45b9-a783-392a2457de42)   
 [\_mm\_sfence](http://msdn.microsoft.com/fr-fr/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/fr-fr/8f03493a-d5f5-4457-892e-0b6540494872)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)