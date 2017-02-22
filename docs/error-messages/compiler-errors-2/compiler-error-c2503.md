---
title: "Erreur du compilateur C2503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2503"
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : les classes de base ne peuvent pas contenir de tableaux de taille zéro  
  
 Une classe ou une structure de base contient un tableau de taille zéro.  Un tableau dans une classe doit avoir au moins un élément.  
  
 L'exemple suivant génère l'erreur C2503 :  
  
```  
// C2503.cpp  
// compile with: /c  
class A {  
   public:  
   int array [];  
};  
  
class B : A {};    // C2503  
  
class C {  
public:  
   int array [10];  
};  
  
class D : C {};  
```