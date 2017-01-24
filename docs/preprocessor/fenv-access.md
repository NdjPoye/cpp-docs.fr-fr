---
title: "fenv_access | Microsoft Docs"
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
  - "vc-pragma.fenv_access"
  - "fenv_access_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fenv_access (pragma)"
  - "pragmas, fenv_access"
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fenv_access
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désactive \(ON\) ou active \(OFF\) les optimisations susceptibles de modifier des tests d'indicateur et des changements de mode.  
  
## Syntaxe  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## Notes  
 Par défaut, `fenv_access` a la valeur OFF.  
  
 Pour plus d'informations sur le comportement en virgule flottante, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Les sortes d'optimisations qui sont soumises à `fenv_access` sont :  
  
-   Élimination globale de sous\-expressions communes  
  
-   Déplacement de code  
  
-   Repli constant  
  
 Les autres pragmas à virgule flottante incluent :  
  
-   [float\_control](../preprocessor/float-control.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## Exemple  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=9.999999776482582e\-003**   
## Exemple  
 L'exemple ci\-dessous se rapporte à un compilateur produisant des fichiers de sortie pour les processeurs Itanium.  **\/fp:precise** conserve les résultats intermédiaires dans une précision étendue où des valeurs supérieures à FLT\_MAX \(3,402823466e\+38F\) peuvent être calculées et, suite à cette somme, aura un résultat 1.0, comme ce devrait être le cas si le calcul était manuel.  **\/fp:strict** conserve les résultats intermédiaires dans leur précision source \(float\) de sorte que la première addition génère un résultat infini, qui est ensuite conservé dans toute l'expression.  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
  **1.000000**   
## Exemple  
 Lorsque vous mettez en commentaires `#pragma fenv_access (on)` dans le code précédent, notez que la sortie change, car le compilateur effectue une évaluation au moment de la compilation, qui n'utilise pas le mode de contrôle.  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **out\=1.000000000000000e\-002**   
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)