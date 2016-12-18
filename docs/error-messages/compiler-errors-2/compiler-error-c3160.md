---
title: "Erreur du compilateur C3160 | Microsoft Docs"
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
  - "C3160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3160"
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointeur' :  les données membres d'une classe managée ou WinRT ne peuvent pas avoir ce type  
  
 Les pointeurs intérieurs de garbage collection peuvent pointer vers l'intérieur d'une classe managée ou WinRT.  Comme ils sont plus lents que les pointeurs d'objet entier et nécessitent un traitement spécial par le récupérateur de mémoire, vous ne pouvez pas déclarer les pointeurs managés intérieurs en tant que membres d'une classe.  
  
 L'exemple suivant génère l'erreur C3160 :  
  
```  
// C3160.cpp  
// compile with: /clr  
ref struct A {  
   // cannot create interior pointers inside a class  
   interior_ptr<int> pg;   // C3160  
   int g;   // OK  
   int* pg2;   // OK  
};  
  
int main() {  
   interior_ptr<int> pg2;   // OK  
}  
```  
  
 **Extensions managées pour C\+\+**  
  
 L'exemple suivant génère l'erreur C3160 :  
  
```  
// C3160b.cpp  
// compile with: /clr:oldSyntax  
  
__gc struct A {  
   // cannot create interior pointers inside a class  
   int __gc* pg; // C3160  
   int g;   // OK  
   int __nogc *pg2;   // OK  
};  
  
int main() {  
   int __gc* pg2;   // OK  
}  
```