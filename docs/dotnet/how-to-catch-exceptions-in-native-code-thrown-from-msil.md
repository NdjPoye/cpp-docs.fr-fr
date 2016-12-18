---
title: "Comment&#160;: intercepter des exceptions en code natif lev&#233;es &#224; partir de MSIL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "intercepter des exceptions, levées depuis MSIL"
  - "exceptions, intercepter"
  - "MSIL, intercepter des exception en code natif"
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: intercepter des exceptions en code natif lev&#233;es &#224; partir de MSIL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En code natif, vous pouvez intercepter l'exception C\+\+ native depuis MSIL.  Vous pouvez intercepter les exceptions CLR avec `__try` et `__except`.  
  
 Pour plus d’informations, consultez [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md) et [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md).  
  
## Exemple  
 L'exemple suivant définit un module avec deux fonctions, une qui provoquent une exception native, et une autre qui provoquent une exception de langage MSIL.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## Exemple  
 L'exemple suivant définit un module qui intercepte une exception native et de langage MSIL.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
  **Erreur**  
**Exception interceptée**   
## Voir aussi  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)