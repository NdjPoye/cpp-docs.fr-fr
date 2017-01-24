---
title: "Erreur du compilateur C3671 | Microsoft Docs"
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
  - "C3671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3671"
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_1' : la fonction ne substitue pas 'fonction\_2'  
  
 Lors de l'utilisation de la syntaxe de substitution explicite, le compilateur génère une erreur si une fonction n'est pas substituée.  Pour plus d'informations, consultez [Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3671 :  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```