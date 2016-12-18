---
title: "__ud2 | Microsoft Docs"
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
  - "__ud2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UD2, instruction"
  - "__ud2, intrinsèque"
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ud2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Génère une instruction non définie.  
  
## Syntaxe  
  
```  
void __ud2();  
```  
  
## Notes  
 Le processeur lève une exception non valide de l'opcode si vous exécutez une instruction non définie.  
  
 La fonction d' `__ud2` équivaut à l'instruction machine d' `UD2` , et est uniquement disponible en mode noyau.  Pour plus d'informations, recherchez le document, « le manuel du développeur de logiciels d'architecture Intel, le volume 2 : référence de jeu d'instructions, » [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) au site.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## détail de FIN Microsoft  
  
## Exemple  
 L'exemple suivant exécute une instruction non définie, qui déclenche une exception.  Le gestionnaire d'exceptions modifie le code de retour de zéro à un de.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
  **avant \_\_ud2 \(\).  Le code de retour \= 0.  dans le gestionnaire d'exceptions.  après \_\_ud2 \(\).  Le code de retour \= 1.**    
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)