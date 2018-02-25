---
title: float_control | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1525b92b43a688cdec970c646613aa4474d44cc3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="floatcontrol"></a>float_control
Spécifie le comportement de virgule flottante d'une fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Indicateurs  
 `value`, `setting` **[push]**  
 Spécifie le comportement de virgule flottante. `value` peut être **précise** ou **sauf**. Pour plus d’informations, consultez l’article [/fp (Spécifier le comportement de virgule flottante)](../build/reference/fp-specify-floating-point-behavior.md). `setting` peut être **sur** ou **hors**.  
  
 Si `value` est **précise**, les paramètres pour **précise** et **sauf** sont spécifiés. **à l’exception de** peut uniquement être définie sur **sur** lorsque **précise** est également défini sur **sur**.  
  
 Si le paramètre facultatif **push** jeton est ajouté, actuel définissant pour `value` est envoyée à la pile interne du compilateur sur.  
  
 **push**  
 Exécute un push du paramètre `float_control` sur la pile interne du compilateur  
  
 **pop**  
 Supprime la `float_control` définition à partir du haut de la pile interne du compilateur et qui rend la nouvelle `float_control` paramètre.  
  
## <a name="remarks"></a>Notes  
 Vous ne pouvez pas activer `float_control precise` off lorsque **sauf** sur. De même, **précise** ne peut pas être mis hors tension lorsque `fenv_access` sur. Pour passer d'un modèle strict à un modèle rapide avec le pragma `float_control`, utilisez le code suivant :  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 Pour passer d'un modèle rapide à un modèle strict avec le pragma `float_control`, utilisez le code suivant :  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 Les autres pragmas à virgule flottante incluent :  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment intercepter une exception à virgule flottante de dépassement de capacité en utilisant le pragma `float_control`.  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)