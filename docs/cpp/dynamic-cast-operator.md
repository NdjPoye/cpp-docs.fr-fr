---
title: "dynamic_cast, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "dynamic_cast"
  - "dynamic_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dynamic_cast (mot clé) (C++)"
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dynamic_cast, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Convertit l'opérande `expression` en un objet de type `type-id`.  
  
## Syntaxe  
  
```  
  
dynamic_cast < type-id > ( expression )  
```  
  
## Notes  
 Le `type-id` doit être un pointeur ou une référence à un type de classe définie précédemment ou un « pointeur vers void ».  Le type d'`expression` doit être un pointeur si `type-id` est un pointeur, ou une l\-value si `type-id` est une référence.  
  
 Consultez [static\_cast](../cpp/static-cast-operator.md) pour obtenir une explication de la différence entre les conversions statiques et dynamiques de casting, et quand il convient d'utiliser chacun.  
  
 Il y deux changements radicaux dans le comportement de `dynamic_cast` dans le code managé :  
  
-   `dynamic_cast` vers un pointeur vers le type sous\-jacent d'un enum boxed échouera pendant l'exécution, retournant 0 au lieu du pointeur converti.  
  
-   `dynamic_cast` ne renverra plus une exception lorsque `type-id` est un pointeur intérieur à un type de valeur, avec le cast ratant au moment de l'exécution.  Le cast retourne maintenant la valeur 0 du pointeur au lieu de renvoyer.  
  
 Si `type-id` est un pointeur vers une classe de base accessible sans ambiguïté directement ou indirectement d'`expression`, un pointeur vers l'unique sous\-objet de type `type-id` sera le résultat.  Par exemple :  
  
```  
// dynamic_cast_1.cpp  
// compile with: /c  
class B { };  
class C : public B { };  
class D : public C { };  
  
void f(D* pd) {  
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class  
                                   // pc points to C subobject of pd   
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class  
                                   // pb points to B subobject of pd  
}  
```  
  
 Ce type de conversion est appelé « upcast » car il déplace un pointeur vers le haut d'une hiérarchie de classes, depuis une classe dérivée jusqu'à une classe dont elle est dérivée.  Un upcast est une conversion implicite.  
  
 Si le `type-id` est void\*, un contrôle à l'exécution est fait pour déterminer le type précis d'`expression`.  Le résultat est un pointeur vers l'objet complet pointé par `expression`.  Par exemple :  
  
```  
// dynamic_cast_2.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = new B;  
   void* pv = dynamic_cast<void*>(pa);  
   // pv now points to an object of type A  
  
   pv = dynamic_cast<void*>(pb);  
   // pv now points to an object of type B  
}  
```  
  
 Si `type-id` n'est pas void\*, un contrôle à l'exécution est fait pour voir si l'objet pointé par `expression` peut être converti dans le type pointé par `type-id`.  
  
 Si le type d'`expression` est une classe de base du type de `type-id`, un contrôle à l'exécution est fait pour voir si `expression` pointe réellement à un objet complet du type de`type-id`.  Si la valeur est true, le résultat est un pointeur vers un objet complet du type de `type-id`.  Par exemple :  
  
```  
// dynamic_cast_3.cpp  
// compile with: /c /GR  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   B* pb = new D;   // unclear but ok  
   B* pb2 = new B;  
  
   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D  
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D  
}  
```  
  
 Ce type de conversion est appelé « cast aval » car il déplace un pointeur vers le bas d'une hiérarchie de classes, d'une classe donnée à une classe dérivée d'elle.  
  
 En cas d'héritage multiple, des possibilités d'ambiguïté sont introduites.  Considérez la hiérarchie de classes affichée dans l'illustration suivante.  
  
 Pour les types CLR, `dynamic_cast` résultent soit dans une absence d'opération si la conversion peut être effectuée implicitement, ou alors dans une instruction MSIL `isinst`, qui exécute un contrôle dynamique et retourne `nullptr` si la conversion échoue.  
  
 L'exemple suivant utilise `dynamic_cast` pour déterminer si une classe est une instance de type particulier :  
  
```  
// dynamic_cast_clr.cpp  
// compile with: /clr  
using namespace System;  
  
void PrintObjectType( Object^o ) {  
   if( dynamic_cast<String^>(o) )  
      Console::WriteLine("Object is a String");  
   else if( dynamic_cast<int^>(o) )  
      Console::WriteLine("Object is an int");  
}  
  
int main() {  
   Object^o1 = "hello";  
   Object^o2 = 10;  
  
   PrintObjectType(o1);  
   PrintObjectType(o2);  
}  
```  
  
 ![Hiérarchie de classes montrant un héritage multiple](../cpp/media/vc39011.png "vc39011")  
Hiérarchie de classes montrant un héritage multiple  
  
 Un pointeur vers un objet de type `D` peut être casté sans risque en `B` ou `C`.  Toutefois, si `D` est casté pour indiquer un objet `A`, quelle instance de `A` sera le résultant ?  Cela entraînerait une erreur d'ambiguë de casting.  Pour contourner ce problème, effectuez deux casts non ambigus.  Par exemple :  
  
```  
// dynamic_cast_4.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   D* pd = new D;  
   B* pb = dynamic_cast<B*>(pd);   // first cast to B  
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous  
}  
```  
  
 D'autres ambiguïtés peuvent être appliquées lorsque vous utilisez les classes de base virtuelles.  Considérez la hiérarchie de classes affichée dans l'illustration suivante.  
  
 ![Hiérarchie de classes montrant des classes de base virtuelles](../cpp/media/vc39012.png "vc39012")  
Hiérarchie de classes montrant des classes virtuelles de base  
  
 Dans cette hiérarchie, `A` est une classe de base virtuelle.  Consultez [Classes de base virtuelle](../misc/virtual-base-classes.md) pour la définition d'une classe de base virtuelle.  À partir d'une instance de classe `E` donné et d'un pointeur au sous\-objet d'`A`, un `dynamic_cast` vers un pointeur vers `B` échouera en raison de l'ambiguïté.  Vous devez d'abord recaster vers l'objet `E` complet, puis remonter jusqu'en haut de la hiérarchie de manière non ambiguë, pour atteinte l'objet correct `B`.  
  
 Considérez la hiérarchie de classes affichée dans l'illustration suivante.  
  
 ![Hiérarchie de classes montrant des classes de base en double](../cpp/media/vc39013.png "vc39013")  
Hiérarchie de classes montrant des classes de base en double  
  
 Soit un objet donné de type `E` et un pointeur vers un sous\-objet d'`D`, pour naviguer du sous\-objet `D` jusqu'au sous\-objet totalement à gauche de `A`, trois conversions peuvent être effectuées.  Effectuez une conversion `dynamic_cast` du pointeur de`D` à un pointeur de`E`, puis une conversion \( `dynamic_cast` ou une conversion implicite\) de `E` à `B`, et enfin une conversion implicite de `B` à `A`.  Par exemple :  
  
```  
// dynamic_cast_5.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   E* pe = dynamic_cast<E*>(pd);  
   B* pb = pe;   // upcast, implicit conversion  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 L'opérateur de`dynamic_cast` peut également être utilisé pour exécuter un « cast croisé ». En utilisant la même hiérarchie de classes, il est possible de convertir un pointeur, par exemple, du sous\-objet d'`B` au sous\-objet d'`D`, tant que l'objet complet est de type `E`.  
  
 Concernant les casts croisés, il est en fait possible d'effectuer la conversion d'un pointeur vers `D` à un pointeur du sous\-objet totalement à gauche `A` en seulement deux étapes.  Effectuez un cast croisé de `D` à `B`, puis une conversion implicite d'un `B` à `A`.  Par exemple :  
  
```  
// dynamic_cast_6.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   B* pb = dynamic_cast<B*>(pd);   // cross cast  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 Une valeur de pointeur null est convertie à la valeur null du pointeur du type de destination par `dynamic_cast`.  
  
 Lorsque vous utilisez `dynamic_cast < type-id > ( expression )`, si `expression` ne peut pas être converti sans risque en type `type-id`, le contrôle à l'exécution entraîne l'échec du cast.  Par exemple :  
  
```  
// dynamic_cast_7.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;  
   // B not derived from A  
}  
```  
  
 La valeur d'un cast ayant échoué vers le type pointeur est un pointeur Null.  Un cast ayant échoué en type référence renvoie une [exception de bad\_cast](../cpp/bad-cast-exception.md).   Si `expression` n'indique pas ou ne référence pas un objet valide, l'exception `__non_rtti_object` sera renvoyée.  
  
 Consultez [typeid](../cpp/typeid-operator.md) pour obtenir une explication de l'exception `__non_rtti_object`.  
  
## Exemple  
 L'exemple suivant crée le pointeur de la classe de base \(struct A\), vers un objet \(struct C\).  Ceci, plus le fait qu'il y a plusieurs fonctions virtuelles, active le polymorphisme d'exécution.  
  
 L'exemple appelle également une fonction non virtuelle dans la hiérarchie.  
  
```  
// dynamic_cast_8.cpp  
// compile with: /GR /EHsc  
#include <stdio.h>  
#include <iostream>  
  
struct A {  
    virtual void test() {  
        printf_s("in A\n");  
   }  
};  
  
struct B : A {  
    virtual void test() {  
        printf_s("in B\n");  
    }  
  
    void test2() {  
        printf_s("test2 in B\n");  
    }  
};  
  
struct C : B {  
    virtual void test() {  
        printf_s("in C\n");  
    }  
  
    void test2() {  
        printf_s("test2 in C\n");  
    }  
};  
  
void Globaltest(A& a) {  
    try {  
        C &c = dynamic_cast<C&>(a);  
        printf_s("in GlobalTest\n");  
    }  
    catch(std::bad_cast) {  
        printf_s("Can't cast to C\n");  
    }  
}  
  
int main() {  
    A *pa = new C;  
    A *pa2 = new B;  
  
    pa->test();  
  
    B * pb = dynamic_cast<B *>(pa);  
    if (pb)  
        pb->test2();  
  
    C * pc = dynamic_cast<C *>(pa2);  
    if (pc)  
        pc->test2();  
  
    C ConStack;  
    Globaltest(ConStack);  
  
   // will fail because B knows nothing about C  
    B BonStack;  
    Globaltest(BonStack);  
}  
```  
  
  **en C**  
**test2 dans B**  
**dans GlobalTest**  
**Impossible d'effectuer un cast vers C**   
## Voir aussi  
 [Opérateurs de casting](../cpp/casting-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)