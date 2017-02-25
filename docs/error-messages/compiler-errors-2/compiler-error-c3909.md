---
title: "Erreur du compilateur C3909 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3909"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3909"
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3909
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une déclaration event WinRT ou managée doit se produire dans un type WinRT ou managé  
  
 Un événement Windows Runtime ou managé a été déclaré dans un type natif.  Pour corriger cette erreur, déclarez les événements dans des types Windows Runtime ou managés.  
  
 Pour plus d'informations, consultez [événement](../../windows/event-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3909 et montre comment la corriger :  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```