---
title: "float_control | Microsoft Docs"
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
  - "vc-pragma.float_control"
  - "float_control_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "float_control (pragma)"
  - "pragmas, float_control"
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: 11
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# float_control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le comportement de virgule flottante d'une fonction.  
  
## Syntaxe  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## Indicateurs  
 `value` *,* `setting` **\[push\]**  
 Spécifie le comportement de virgule flottante.  `value` peut avoir la valeur **precise** ou **except**.  Pour plus d'informations, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../build/reference/fp-specify-floating-point-behavior.md).  `setting` peut avoir la valeur **on** ou **off**.  
  
 Si `value` a la valeur **precise**, les paramètres de **precise** et **except** sont spécifiés.  **except** peut être défini sur **on** lorsque **precise** est aussi défini sur **on**.  
  
 Si le jeton **push** facultatif est ajouté, le paramètre actuel pour `value` fait l'objet d'un push vers la pile interne du compilateur.  
  
 **push**  
 Exécute un push du paramètre `float_control` sur la pile interne du compilateur  
  
 **pop**  
 Supprime le paramètre`float_control` du haut de la pile interne du compilateur et crée le nouveau paramètre `float_control`.  
  
## Notes  
 Vous ne pouvez pas désactiver `float_control precise` lorsque **except** est activé.  De même, **precise** ne peut pas être désactivé lorsque `fenv_access` est activé.  Pour passer d'un modèle strict à un modèle rapide avec le pragma `float_control`, utilisez le code suivant :  
  
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
  
-   [fenv\_access](../preprocessor/fenv-access.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## Exemple  
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
  
  **Correct**   
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)