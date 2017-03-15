---
title: "Erreur du compilateur C2247 | Microsoft Docs"
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
  - "C2247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2247"
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' non accessible, car 'classe' utilise 'spécificateur' pour hériter de 'classe'  
  
 `identifier` est hérité d'une classe déclarée avec accès privé ou protégé.  
  
 L'exemple suivant génère l'erreur C2247 :  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003 : contrôle d'accès avec membres protégés.  Un membre protégé \(n\) est uniquement accessible par l'intermédiaire d'une fonction membre d'une classe \(B\) qui hérite de la classe \(A\) dont il est \(n\) membre.  
  
 Pour produire un code qui est valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+, déclarez le nombre en tant que friend du type.  Un héritage public pourrait également être employé.  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 L'erreur C2247 peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003 : classes de base privées maintenant inaccessibles.  Une classe \(A\) qui est une classe de base privée pour un type \(B\) ne devrait pas être accessible pour un type \(C\) qui utilise B comme classe de base.  
  
 Pour produire un code qui est valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+, utilisez l'opérateur de portée.  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```