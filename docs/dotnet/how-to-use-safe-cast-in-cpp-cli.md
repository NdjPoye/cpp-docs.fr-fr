---
title: "Comment&#160;: utiliser safe_cast dans C++/CLI | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "safe_cast (mot clé C++), cast ascendant"
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: utiliser safe_cast dans C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment utiliser le safe\_cast dans les applications ODBC [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  Pour plus d'informations sur le safe\_cast dans [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], consultez [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
## Cast ascendant  
 Un upcast est une conversion d'un type dérivé en une de ses classes de base.  Cette conversion est sécurisé et ne nécessite pas une notation de conversion explicite.  L'exemple suivant montre comment effectuer un upcast, avec `safe_cast` et sans lui.  
  
```  
// safe_upcast.cpp  
// compile with: /clr  
using namespace System;  
interface class A {  
   void Test();  
};  
  
ref struct B : public A {  
   virtual void Test() {  
      Console::WriteLine("in B::Test");  
   }  
  
   void Test2() {  
      Console::WriteLine("in B::Test2");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {  
      Console::WriteLine("in C::Test");  
   };  
};  
  
int main() {  
   C ^ c = gcnew C;  
  
   // implicit upcast  
   B ^ b = c;  
   b->Test();  
   b->Test2();  
  
   // upcast with safe_cast  
   b = nullptr;  
   b = safe_cast<B^>(c);  
   b->Test();  
   b->Test2();  
}  
```  
  
  **dans C::Test**  
**dans B::Test2**  
**dans C::Test**  
**dans B::Test2**   
## Cast descendant  
 Une conversion aval est un cast de la classe de base pour une classe dérivée de la classe de base.  Une conversion aval n'est sécurisée que si l'objet qui est traité au moment de l'exécution adresse en fait un objet de la classe dérivée.  Contrairement à `static_cast`, `safe_cast` effectue une vérification dynamique et lève <xref:System.InvalidCastException> si la conversion échoue.  
  
```  
// safe_downcast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class A { void Test(); };  
  
ref struct B : public A {  
   virtual void Test() {   
      Console::WriteLine("in B::Test()");  
   }  
  
   void Test2() {   
      Console::WriteLine("in B::Test2()");  
   }  
};  
  
ref struct C : public B {  
   virtual void Test() override {   
      Console::WriteLine("in C::Test()");  
   }  
};  
  
interface class I {};  
  
value struct V : public I {};  
  
int main() {  
   A^ a = gcnew C();  
   a->Test();  
   B^ b = safe_cast<B^>(a);  
   b->Test();  
   b->Test2();  
  
   V v;   
   I^ i = v;   // i boxes V  
   V^ refv = safe_cast<V^>(i);   
  
   Object^ o = gcnew B;  
   A^ a2= safe_cast<A^>(o);  
}  
```  
  
  **dans C::Test\(\)**  
**dans C::Test\(\)**  
**dans B::Test2\(\)**   
## safe\_cast avec des conversions définies par l'utilisateur.  
 L'exemple suivant montre comment utiliser `safe_cast` pour appeler des conversions définies par l'utilisateur.  
  
```  
// safe_cast_udc.cpp  
// compile with: /clr  
using namespace System;  
value struct V;  
  
ref struct R {  
   int x;  
   R() {  
      x = 1;  
   }  
  
   R(int argx) {  
      x = argx;  
   }  
  
   static operator R::V^(R^ r);  
};  
  
value struct V {  
   int x;  
   static operator R^(V& v) {  
      Console::WriteLine("in operator R^(V& v)");  
      R^ r = gcnew R();  
      r->x = v.x;    
      return r;  
   }  
  
   V(int argx) {  
      x = argx;  
   }  
};  
  
   R::operator V^(R^ r) {  
      Console::WriteLine("in operator V^(R^ r)");  
      return gcnew V(r->x);  
   }  
  
int main() {  
   bool fReturnVal = false;  
   V v(2);  
   R^ r = safe_cast<R^>(v);   // should invoke UDC  
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC  
}  
```  
  
  **dans l'opérateur R^ \(V& v**  
**dans l'opérateur R^ \(R^ R\)**   
## opérations de safe\_cast et de boxing  
 **Boxing**  
  
 Le boxing est défini comme une conversion injectée par le compilateur et définie par l'utilisateur.  Par conséquent, vous pouvez utiliser `safe_cast` pour encadrer une valeur sur le segment CLR.  
  
 L'exemple suivant montre le boxing avec des types de valeur simples et définis par l'utilisateur.  Un `safe_cast` enferme un type de valeur de variable qui se trouve dans la pile native afin qu'il puisse être affecté à une variable sur le segment récupérés par le garbage collector.  
  
```  
// safe_cast_boxing.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct V : public I {   
   int m_x;  
  
   V(int i) : m_x(i) {}  
};  
  
int main() {  
   // box a value type  
   V v(100);  
   I^ i = safe_cast<I^>(v);  
  
   int x = 100;  
   V^ refv = safe_cast<V^>(v);  
   int^ refi = safe_cast<int^>(x);  
}  
```  
  
 L'exemple suivant montre que le boxing est prioritaire sur une conversion définie par l'utilisateur dans une opération de `safe_cast`.  
  
```  
// safe_cast_boxing_2.cpp  
// compile with: /clr  
static bool fRetval = true;  
  
interface struct I {};  
value struct V : public I {  
   int x;  
  
   V(int argx) {  
      x = argx;  
   }  
  
   static operator I^(V v) {  
      fRetval = false;  
      I^ pi = v;  
      return pi;  
   }  
};  
  
ref struct R {  
   R() {}  
   R(V^ pv) {}  
};  
  
int main() {  
   V v(10);  
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"  
}  
```  
  
 **Unboxing**  
  
 L'unboxing est défini comme une conversion injectée par le compilateur et définie par l'utilisateur.  Par conséquent, vous pouvez utiliser `safe_cast` pour désencadrer une valeur sur le segment CLR.  
  
 La conversion unboxing est une conversion définie par l'utilisateur, mais contrairement au boxing, la conversion unboxing doit être explicite\- autrement dit, elle doit être effectuée par un cast `static_cast` de type C, ou un `safe_cast` ; l'unboxing ne peut pas être exécuté de manière implicite.  
  
```  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 L'exemple suivant illustre la conversion unboxing avec les types de valeurs et les types de primitive.  
  
```  
// safe_cast_unboxing_2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct I {};  
  
value struct VI : public I {};  
  
void test1() {  
   Object^ o = 5;  
   int x = safe_cast<Int32>(o);  
}  
  
value struct V {  
   int x;  
   String^ s;  
};  
  
void test2() {  
   V localv;  
   Object^ o = localv;  
   V unboxv = safe_cast<V>(o);  
}  
  
void test3() {  
   V localv;  
   V^ o2 = localv;  
   V unboxv2 = safe_cast<V>(o2);  
}  
  
void test4() {  
   I^ refi = VI();  
   VI vi  = safe_cast<VI>(refi);  
}  
  
int main() {  
   test1();  
   test2();  
   test3();  
   test4();  
}  
```  
  
## types de safe\_cast et de générique  
 L'exemple suivant montre comment utiliser `safe_cast` pour effectuer une conversion aval avec un type générique.  
  
```  
// safe_cast_generic_types.cpp  
// compile with: /clr  
interface struct I {};  
  
generic<class T> where T:I  
ref struct Base {  
   T t;  
   void test1() {}  
};  
  
generic<class T> where T:I  
ref struct Derived:public Base <T> {};  
  
ref struct R:public I {};  
  
typedef Base<R^> GBase_R;  
typedef Derived<R^> GDerived_R;  
  
int main() {  
   GBase_R^ br = gcnew GDerived_R();  
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);  
}  
```  
  
## Voir aussi  
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)