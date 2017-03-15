---
title: "Comment&#160;: demander explicitement le boxing | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversion boxing, demander explicitement"
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Comment&#160;: demander explicitement le boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez demander explicitement le boxing en affectant une variable à une variable de type `Object`.  
  
## Exemple  
  
```  
// vcmcppv2_explicit_boxing3.cpp  
// compile with: /clr  
using namespace System;  
  
void f(int i) {  
   Console::WriteLine("f(int i)");  
}  
  
void f(Object ^o) {  
   Console::WriteLine("f(Object^ o)");  
}  
  
int main() {  
   int i = 5;  
   Object ^ O = i;   // forces i to be boxed  
   f(i);  
   f(O);  
   f( (Object^)i );  // boxes i  
}  
```  
  
  **f \(int i\)**  
**f\(Object^ o\)**  
**f\(Object^ o\)**   
## Voir aussi  
 [Boxing](../windows/boxing-cpp-component-extensions.md)