---
title: fenv_access | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f06c699ba20d09ec1d013f9464af02935da9f9c1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="fenvaccess"></a>fenv_access
Désactive (ON) ou active (OFF) les optimisations susceptibles de modifier des tests d'indicateur et des changements de mode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## <a name="remarks"></a>Notes  
 Par défaut, `fenv_access` a la valeur OFF.  
  
 Pour plus d’informations sur le comportement de virgule flottante, consultez [/fp (spécifier du comportement de nombres à virgule flottante)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Les sortes d'optimisations qui sont soumises à `fenv_access` sont :  
  
-   Élimination globale de sous-expressions communes  
  
-   Déplacement de code  
  
-   Repli constant  
  
 Les autres pragmas à virgule flottante incluent :  
  
-   [float_control](../preprocessor/float-control.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
out=9.999999776482582e-003  
```  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous se rapporte à un compilateur produisant des fichiers de sortie pour les processeurs Itanium. **/ fp : precise** conserve les résultats intermédiaires dans une précision étendue où les valeurs supérieures à FLT_MAX (3, 402823466e + 38F) peuvent être calculées et à la suite de cette somme aura 1.0 résultat, comme il le devrait si calculé manuellement. **/ fp : strict** conserve les résultats intermédiaires dans leur précision source (float) pour la première addition génère un résultat infini, qui est conservée tout au long de l’expression.  
  
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
  
```Output  
1.000000  
```  
  
## <a name="example"></a>Exemple  
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
  
```Output  
out=1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)