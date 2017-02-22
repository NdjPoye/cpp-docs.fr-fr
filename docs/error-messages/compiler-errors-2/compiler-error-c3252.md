---
title: "Compiler Error C3252 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3252"
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compiler Error C3252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'méthode' : impossible de réduire l'accessibilité d'une méthode virtuelle dans un type managé ou WinRT  
  
 Une classe qui implémente une méthode virtuelle à partir d'une classe de base ou n'importe quelle méthode à partir d'une interface ne peut pas réduire l'accès de cette méthode.  
  
 Notez que toutes les méthodes dans une interface sont publiques.  
  
 L'exemple suivant génère l'erreur C3252 et montre comment la corriger :  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```