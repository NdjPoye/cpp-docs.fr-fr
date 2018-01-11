---
title: Erreur du compilateur C2327 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2327
dev_langs: C++
helpviewer_keywords: C2327
ms.assetid: 95278c95-d1f9-4487-ad27-53311f5e8112
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17aa5635f6e1185e68d3042009f677d797a11a78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2327"></a>Erreur du compilateur C2327
'symbole' : n’est pas un nom de type, statique ou énumérateur  
  
 Le code dans une classe imbriquée tente d’accéder à un membre de la classe englobante qui n’est pas un nom de type, un membre statique ou un énumérateur.  
  
 Lors de la compilation avec **/CLR**, une cause fréquente de l’erreur C2327 est une propriété portant le même nom que le type de propriété.  
  
 L’exemple suivant génère l’erreur C2327 :  
  
```  
// C2327.cpp  
int x;  
class enclose {  
public:  
   int x;  
   static int s;  
   class inner {  
      void f() {  
         x = 1;   // C2327; enclose::x is not static  
         s = 1;   // ok; enclose::s is static  
         ::x = 1;   // ok; ::x refers to global  
      }  
   };  
};  
```  
  
 L’erreur C2327 peut également se produire si le nom d’un type est masqué par le nom d’un membre :  
  
```  
// C2327b.cpp  
class X {};  
  
class S {  
   X X;  
   // try the following line instead  
   // X MyX;  
   X other;   // C2327, rename member X  
};  
```  
  
 L’erreur C2327 peut également se déclencher dans ce cas, où vous devez spécifier complètement le type de données du paramètre :  
  
```  
// C2327c.cpp  
// compile with: /c  
struct A {};  
  
struct B {  
   int A;  
   void f(A a) {   // C2327  
   void f2(struct A a) {}   // OK  
   }  
};  
```  
  
 L’exemple suivant génère l’erreur C2327 :  
  
```  
// C2327d.cpp  
// compile with: /clr /c  
using namespace System;  
  
namespace NA {  
   public enum class E : Int32 {  
      one = 1,  
      two = 2,  
      three = 3  
   };  
  
   public ref class A {  
   private:  
      E m_e;  
   public:  
      property E E {  
         NA::E get() {  
            return m_e;  
         }  
         // At set, compiler doesn't know whether E is get_E or   
         // Enum E, therefore fully qualifying Enum E is necessary  
         void set( E e ) {   // C2327  
            // try the following line instead  
            // void set(NA::E e) {  
            m_e = e;  
         }  
      }  
   };  
}  
```  
  
L’exemple suivant illustre l’erreur C2327 lorsqu’une propriété a le même nom que le type de propriété :  
  
```  
// C2327f.cpp  
// compile with: /clr /c  
public value class Address {};  
  
public ref class Person {  
public:  
   property Address Address {  
      ::Address get() {     
         return address;  
      }  
      void set(Address addr) {   // C2327  
      // try the following line instead  
      // set(::Address addr) {  
         address = addr;   
      }  
   }  
private:  
   Address address;   // C2327  
   // try the following line instead  
   // ::Address address;  
};  
```  
