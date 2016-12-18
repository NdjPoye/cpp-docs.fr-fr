---
title: "deprecated (C/C++) | Microsoft Docs"
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
  - "vc-pragma.deprecated"
  - "deprecated_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "deprecated (pragma)"
  - "pragmas, deprecated"
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# deprecated (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le pragma **déconseillé** vous permet d'indiquer qu'une fonction, un type ou tout autre identificateur ne peut plus être pris en charge dans une future version ou ne doit plus être utilisé.  
  
## Syntaxe  
  
```  
  
#pragma deprecated( identifier1 [,identifier2, ...] )  
```  
  
## Notes  
 Lorsque le compilateur rencontre un symbole déconseillé, il émet [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).  
  
 Vous pouvez désapprouver des noms de macros.  Placez le nom de la macro entre guillemets, sinon une expansion macro va se produire.  
  
 Le modificateur [déconseillé](../cpp/deprecated-cpp.md) `__declspec` vous permet de spécifier l'état déconseillé pour les formes spéciales des fonctions surchargées.  
  
## Exemple  
  
```  
// pragma_directive_deprecated.cpp  
// compile with: /W3  
#include <stdio.h>  
void func1(void) {  
}  
  
void func2(void) {  
}  
  
int main() {  
   func1();  
   func2();  
   #pragma deprecated(func1, func2)  
   func1();   // C4995  
   func2();   // C4995  
}  
```  
  
 L'exemple suivant montre comment déconseiller une classe :  
  
```  
// pragma_directive_deprecated2.cpp  
// compile with: /W3  
#pragma deprecated(X)  
class X {  // C4995  
public:  
   void f(){}  
};  
  
int main() {  
   X x;   // C4995  
}  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)