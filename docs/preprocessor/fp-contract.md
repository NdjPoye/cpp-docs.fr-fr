---
title: "fp_contract | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fp_contract"
  - "fp_contract_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fp_contract (pragma)"
  - "pragmas, fp_contract"
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fp_contract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine si la contraction à virgule flottante doit être effectuée.  
  
## Syntaxe  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## Notes  
 Par défaut, `fp_contract` a pour valeur ON.  
  
 Pour plus d'informations sur le comportement en virgule flottante, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Les autres pragmas à virgule flottante incluent :  
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [float\_control](../preprocessor/float-control.md)  
  
## Exemple  
 Le code généré à partir de cet exemple n'utilise pas l'instruction **fma** \(Fused Multiply Add\) sur les processeurs Itanium.  Si vous placez en commentaires `#pragma fp_contract (off)`, le code généré utilise l'instruction **fma**.  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
  **out\=0.000000000000000e\+000**  
**out\=6.152500152587891e\+001**  
**out\=2.351000061035156e\+002**  
**out\=5.207249755859375e\+002**  
**out\=9.184000244140625e\+002**  
**out\=1.428125000000000e\+003**  
**out\=2.049899902343750e\+003**  
**out\=2.783724853515625e\+003**  
**out\=3.629600097656250e\+003**  
**out\=4.587524902343750e\+003**   
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)