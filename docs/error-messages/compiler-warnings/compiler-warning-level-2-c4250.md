---
title: "Avertissement du compilateur (niveau 2) C4250 | Microsoft Docs"
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
  - "C4250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4250"
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe1' : hérite de 'classe2::membre' via la dominance  
  
 Deux ou plusieurs membres ont le même nom.  Celui de `class2` est hérité parce que c'est une classe de base pour les autres classes qui contenaient ce membre.  
  
 Pour supprimer l'erreur C4250, utilisez le pragma [warning](../../preprocessor/warning.md).  
  
 Comme une classe de base virtuelle est partagée entre plusieurs classes dérivées, un nom dans une classe dérivée domine un nom dans une classe de base.  Par exemple, dans la hiérarchie de classes suivante, il existe deux définitions de func héritées dans un losange : l'instance de vbc::func\(\) dans la classe faible, et l'instance de dominant::func\(\) dans la classe dominante.  Un appel non qualifié de func\(\) par l'intermédiaire d'un objet de classe en losange, appelle toujours l'instance de dominate::func\(\).  Si la classe faible devait introduire une instance de func\(\), aucune définition ne dominerait, et l'appel serait signalé comme ambigu.  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4250 :  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## Exemple  
 Cet exemple illustre une situation plus complexe.  L'exemple suivant génère l'erreur C4250 :  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```