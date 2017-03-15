---
title: "D&#233;claration using | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "déclaration using"
  - "déclarer des espaces de noms, noms non qualifiés dans les espaces de noms"
  - "déclarations [C++], déclaration using"
  - "espaces de noms [C++], noms non qualifiés dans"
  - "using, mot clé [C++]"
  - "déclarations [C++], espaces de noms"
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# D&#233;claration using
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La déclaration `using` introduit un nom dans la zone déclarative dans laquelle la déclaration `using` apparait.  
  
## Syntaxe  
  
```  
  
      using [typename][::] nested-name-specifier unqualified-id  
using :: unqualified-id  
```  
  
## Notes  
 Le nom devient un synonyme pour une entité déclarée ailleurs.  Il permet à un nom *individuel* venant d'un espace de noms spécifique à être utilisé sans [qualification explicite](../misc/explicit-qualification.md).  Ceci contraste avec la directive `using`, qui permet à *tout* nom d'un espace de noms d'être utilisé sans qualification.  Pour plus d'informations, consultez [using Directive](../misc/using-directive-cpp.md).  Ce mot clé est également utilisé pour [type aliases](../cpp/aliases-and-typedefs-cpp.md).  
  
## Exemple  
 Une déclaration using peut être utilisé dans une définition de classe.  
  
```cpp  
// using_declaration1.cpp  
#include <stdio.h>  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class D : B {  
public:  
   using B::f;  
   using B::g;  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
  **Dans D::f\(\)**  
**Dans B::f\(\)**  
**Dans B::g\(\)**   
## Exemple  
 Lorsqu'elle est utilisée pour déclarer un membre, une déclaration using doit faire référence à un membre d'une classe de base.  
  
```cpp  
// using_declaration2.cpp  
#include <stdio.h>  
  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class C {  
public:  
   int g();  
};  
  
class D2 : public B {  
public:  
   using B::f;   // ok: B is a base of D2  
   // using C::g;   // error: C isn't a base of D2  
};  
  
int main() {  
   D2 MyD2;  
   MyD2.f('a');  
}  
```  
  
  **Dans B::f\(\)**   
## Exemple  
 Les membres déclarés avec une déclaration using peuvent être référencés à l'aide d'une qualification explicite.  Le préfixe `::` fait référence à l'espace de noms global.  
  
```cpp  
// using_declaration3.cpp  
#include <stdio.h>  
  
void f() {  
   printf_s("In f\n");  
}  
  
namespace A {  
   void g() {  
      printf_s("In A::g\n");  
   }  
}  
  
namespace X {  
   using ::f;   // global f  
   using A::g;   // A's g  
}  
  
void h() {  
   printf_s("In h\n");  
   X::f();   // calls ::f  
   X::g();   // calls A::g  
}  
  
int main() {  
   h();  
}  
```  
  
  **Dans h**  
**Dans f**  
**Dans A::g**   
## Exemple  
 Lorsque une déclaration using est crée, le synonyme créé par la déclaration fait uniquement référence aux définitions valides au point de la déclaration using.  Les définitions ajoutées à un espace de noms après la déclaration using sont des synonymes non valides.  
  
 Un nom défini par une déclaration using est un alias de son nom d'origine.  Il n'affecte pas le type, la liaison ou d'autres attributs de la déclaration d'origine.  
  
```cpp  
// post_declaration_namespace_additions.cpp  
// compile with: /c  
namespace A {  
   void f(int) {}  
}  
  
using A::f;   // f is a synonym for A::f(int) only  
  
namespace A {  
   void f(char) {}  
}  
  
void f() {  
   f('a');   // refers to A::f(int), even though A::f(char) exists  
}  
  
void b() {  
   using A::f;   // refers to A::f(int) AND A::f(char)  
   f('a');   // calls A::f(char);  
}  
```  
  
## Exemple  
 En ce qui concerne les fonctions des espaces de noms, si un ensemble de déclarations locales et les déclarations using pour un nom unique sont donnés dans la région déclarative, ils doivent tous faire référence à la même entité, ou ils doivent tous référencer des fonctions.  
  
```cpp  
// functions_in_namespaces1.cpp  
// C2874 expected  
namespace B {  
    int i;  
    void f(int);  
    void f(double);  
}  
  
void g() {  
    int i;  
    using B::i;   // error: i declared twice  
    void f(char);  
    using B::f;   // ok: each f is a function  
}  
```  
  
 Dans l'exemple ci\-dessus, l'instruction `using B::i` fait déclarer un deuxième `int i`dans la fonction `g()`.  L'instruction `using B::f` n'est pas en conflit avec la fonction `f(char)` parce que les noms de fonctions introduits par `B::f` ont des types de paramètres différents.  
  
## Exemple  
 Une déclaration de fonction locale ne peut pas avoir le même nom et type qu'une fonction introduite en utilisant la déclaration.  Par exemple :  
  
```cpp  
// functions_in_namespaces2.cpp  
// C2668 expected  
namespace B {  
    void f(int);  
    void f(double);  
}  
  
namespace C {  
    void f(int);  
    void f(double);  
    void f(char);  
}  
  
void h() {  
    using B::f;          // introduces B::f(int) and B::f(double)  
    using C::f;          // C::f(int), C::f(double), and C::f(char)  
    f('h');              // calls C::f(char)  
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?  
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)  
}  
```  
  
## Exemple  
 En ce qui concerne l'héritage, lorsque une déclaration using introduit un nom d'une classe de base dans une portée de classe dérivée, les fonctions membres de la classe dérivée se substituent aux fonctions membres virtuelles ayant le même nom et les mêmes types d'argument dans la classe de base.  
  
```cpp  
// using_declaration_inheritance1.cpp  
#include <stdio.h>  
struct B {  
   virtual void f(int) {  
      printf_s("In B::f(int)\n");  
   }  
  
   virtual void f(char) {  
      printf_s("In B::f(char)\n");  
   }  
  
   void g(int) {  
      printf_s("In B::g\n");  
   }  
  
   void h(int);  
};  
  
struct D : B {  
   using B::f;  
   void f(int) {   // ok: D::f(int) overrides B::f(int)  
      printf_s("In D::f(int)\n");  
   }  
  
   using B::g;  
   void g(char) {   // ok: there is no B::g(char)  
      printf_s("In D::g(char)\n");  
   }  
  
   using B::h;  
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)  
};  
  
void f(D* pd) {  
   pd->f(1);   // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);   // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
  **Dans D::f \(entier\)**  
**Dans B::f \(char\)**  
**Dans B::g**  
**Dans D::g \(char\)**   
## Exemple  
 Toutes les instances d'un nom mentionné dans une déclaration using doivent être accessibles.  En particulier, si une classe dérivée utilise une déclaration using pour accéder à un membre d'une classe de base, le nom de membre doit être accessible.  Si le nom est celui d'une fonction membre surchargée, alors toutes les fonctions nommées doivent être accessibles.  
  
 Consultez [Contrôle d'accès des membres](../cpp/member-access-control-cpp.md), pour plus d'informations sur l'accessibilité des membres.  
  
```cpp  
// using_declaration_inheritance2.cpp  
// C2876 expected  
class A {  
private:  
   void f(char);  
public:  
   void f(int);  
protected:  
   void g();  
};  
  
class B : public A {  
   using A::f;   // C2876: A::f(char) is inaccessible  
public:  
   using A::g;   // B::g is a public synonym for A::g  
};  
```  
  
## Voir aussi  
 [Espaces de noms](../cpp/namespaces-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)