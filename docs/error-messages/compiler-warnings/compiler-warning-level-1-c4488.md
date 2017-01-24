---
title: "Avertissement du compilateur (niveau 1) C4488 | Microsoft Docs"
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
  - "C4488"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4488"
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4488
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : requiert le mot clé 'MotClé' pour implémenter la méthode d'interface 'méthode\_interface'  
  
 Une classe doit implémenter tous les membres d'une interface dont elle hérite directement.  Un membre implémenté doit disposer d'un accès public et être marqué virtual.  
  
## Exemple  
 L'erreur C4488 peut se produire si un membre implémenté n'est pas public.  L'exemple suivant génère l'erreur C4488 :  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## Exemple  
 L'erreur C4488 peut se produire si un membre implémenté n'est pas marqué virtual.  L'exemple suivant génère l'erreur C4488 :  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```