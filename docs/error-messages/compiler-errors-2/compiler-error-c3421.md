---
title: "Erreur du compilateur C3421 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3421"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3421"
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3421
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : vous ne pouvez pas appeler le finaliseur de cette classe, car il est soit inaccessible, soit inexistant  
  
 Un finaliseur est implicitement privé. Il ne peut donc pas être appelé en dehors de son type englobant.  
  
 Pour plus d'informations, consultez [Destructeurs et finaliseurs dans Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3421.  
  
```  
// C3421.cpp // compile with: /clr ref class A {}; ref class B { !B() {} public: ~B() {} }; int main() { A a; a.!A();   // C3421 B b; b.!B();   // C3421 }  
```