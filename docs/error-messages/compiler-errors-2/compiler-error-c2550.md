---
title: "Erreur du compilateur C2550 | Microsoft Docs"
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
  - "C2550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2550"
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les listes d'initialiseurs de constructeur ne sont autorisées que dans la définition d'un constructeur  
  
 Une liste d'initialiseurs de classes de base est utilisée dans la définition d'une fonction qui n'est pas un constructeur.  
  
 L'exemple suivant génère l'erreur C2550 :  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```