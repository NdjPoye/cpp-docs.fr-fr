---
title: "Erreur du compilateur C2139 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2139"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2139"
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2139
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe non définie n'est pas autorisée en tant qu'argument pour un trait de type intrinsèque du compilateur 'trait'  
  
 Un argument non valide a été passé à un trait de type.  
  
 Pour plus d'informations, consultez [Compiler Support for Type Traits](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2139 :  
  
```  
// C2139.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class C;  
class D {};  
  
class E {  
public:  
   virtual void Test() {}  
};  
  
int main() {  
   cout << is_polymorphic<C>::value << endl;   // C2139  
   cout << is_polymorphic<D>::value << endl;   // OK  
   cout << is_polymorphic<E>::value << endl;   // OK  
}  
```