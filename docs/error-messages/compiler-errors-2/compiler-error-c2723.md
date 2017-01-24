---
title: "Erreur du compilateur C2723 | Microsoft Docs"
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
  - "C2723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2723"
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : spécificateur 'spécificateur' non conforme sur la définition d'une fonction  
  
 Le spécificateur ne peut pas apparaître avec une définition de fonction en dehors d'une déclaration de classe.  Le spécificateur `virtual` peut être spécifié uniquement sur une déclaration de fonction membre dans une déclaration de classe.  
  
 L'exemple suivant génère l'erreur C2723 et montre comment la corriger :  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```