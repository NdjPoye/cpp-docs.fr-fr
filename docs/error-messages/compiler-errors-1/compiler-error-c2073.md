---
title: "Erreur du compilateur C2073 | Microsoft Docs"
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
  - "C2073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2073"
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : les éléments d'un tableau partiellement initialisé nécessitent un constructeur par défaut  
  
 Trop peu d'initialiseurs ont été spécifiés pour un tableau de types ou de constantes définis par l'utilisateur.  Si un initialiseur explicite et le constructeur correspondant ne sont pas spécifiés pour un membre d'un tableau, un constructeur par défaut doit être fourni.  
  
 L'exemple suivant génère l'erreur C2073 :  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```