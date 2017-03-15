---
title: "Erreur du compilateur C3662 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3662"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3662"
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur du compilateur C3662
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : spécificateur de substitution 'spécificateur' uniquement autorisé sur les fonctions membres de classes managées ou WinRT  
  
 Un spécificateur de substitution a été utilisé sur un membre de type natif, ce qui n'est pas autorisé.  
  
 Pour plus d'informations, voir [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3662.  
  
```  
// C3662.cpp  
// compile with: /clr /c  
struct S {  
   virtual void f();  
};  
  
struct S1 : S {  
   virtual void f() new;   // C3662  
};  
  
ref struct T {  
   virtual void f();  
};  
  
ref struct T1 : T {  
   virtual void f() new;   // OK  
};  
```