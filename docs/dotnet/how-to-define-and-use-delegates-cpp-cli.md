---
title: "Comment&#160;: d&#233;finir et utiliser des d&#233;l&#233;gu&#233;s (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "délégués"
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;finir et utiliser des d&#233;l&#233;gu&#233;s (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment définir et utiliser les délégués dans [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  
  
 Bien que le .NET Framework fournisse plusieurs délégués, vous devrez peut\-être définir de nouveaux délégués.  
  
 L'exemple suivant définit un délégué d'événement nommé `MyCallback`.  Le code de gestion des événements \(fonction appelée lorsque ce nouveau délégué est déclenché\) doit être de type de retour `void` et prendre une référence <xref:System.String>.  
  
 La fonction principale utilise une méthode statique définie par `SomeClass` pour instancier le délégué de `MyCallback`.  Le délégué devient méthode alternative pour appeler cette fonction, comme illustré en envoyant la chaîne « single » sur l'objet délégué.  Les instances supplémentaires `MyCallback` sont liées ensemble puis exécutées par un appel à l'objet délégué.  
  
```  
// use_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
ref class SomeClass  
{  
public:  
   static void Func(String^ str)  
   {  
      Console::WriteLine("static SomeClass::Func - {0}", str);  
   }  
};  
  
ref class OtherClass  
{  
public:  
   OtherClass( Int32 n )   
   {  
      num = n;  
   }  
  
   void Method(String^ str)   
   {  
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",   
         str, num);  
   }  
  
   Int32 num;  
};  
  
delegate void MyCallback(String^ str);  
  
int main( )   
{  
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);     
   callback("single");   
  
   callback += gcnew MyCallback(SomeClass::Func);     
  
   OtherClass^ f = gcnew OtherClass(99);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   f = gcnew OtherClass(100);  
   callback += gcnew MyCallback(f, &OtherClass::Method);  
  
   callback("chained");  
  
   return 0;  
}  
```  
  
 **Sortie**  
  
  **static SomeClass::Func \- single**  
**static SomeClass::Func \- chained**  
**static SomeClass::Func \- chained**  
**OtherClass::Method \- chained, num \= 99**  
**OtherClass::Method \- chained, num \= 100** L'exemple de code suivant montre comment associer un délégué à un membre d'une plage de valeurs.  
  
```  
// mcppv2_del_mem_value_class.cpp  
// compile with: /clr  
using namespace System;  
public delegate void MyDel();  
  
value class A {  
public:  
   void func1() {  
      Console::WriteLine("test");  
   }  
};  
  
int main() {  
   A a;  
   A^ ah = a;  
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a  
   f();  
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);  
   f2();  
}  
```  
  
 **Sortie**  
  
  **tester**  
**tester**   
## Comment composer des délégués  
 Utilisez l'opérateur `-` pour supprimer un délégué composant d'un délégué composé  
  
```  
// mcppv2_compose_delegates.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDelegate(String ^ s);  
  
ref class MyClass {  
public:  
   static void Hello(String ^ s) {  
      Console::WriteLine("Hello, {0}!", s);  
   }  
  
   static void Goodbye(String ^ s) {  
      Console::WriteLine("  Goodbye, {0}!", s);  
   }  
};  
  
int main() {  
  
   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);  
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);  
   MyDelegate ^ c = a + b;  
   MyDelegate ^ d = c - a;  
  
   Console::WriteLine("Invoking delegate a:");  
   a("A");  
   Console::WriteLine("Invoking delegate b:");  
   b("B");  
   Console::WriteLine("Invoking delegate c:");  
   c("C");  
   Console::WriteLine("Invoking delegate d:");  
   d("D");  
}  
```  
  
 **Sortie**  
  
  **Appeler le délégué a :**  
**Hello, A\!**  
**Appeler le délégué b :**  
 **Goodbye, B\!**  
**Appeler le délégué c:**  
**Hello, C\!**  
 **Goodbye, C\!**  
**Appeler le délégué d :**  
 **Goodbye, D\!**   
## Passer un délégué^ vers une fonction native qui attend un pointeur de fonction.  
 Depuis un composant managé vous pouvez appeler une fonction native avec des paramètres de pointeur fonction où la fonction native peut ensuite appeler la fonction membre du délégué du composant managé.  
  
 Cet exemple crée la .dll qui exporte la fonction native :  
  
```  
// delegate_to_native_function.cpp  
// compile with: /LD  
#include < windows.h >  
extern "C" {  
   __declspec(dllexport)  
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {  
      mgdFunc("Call to Managed Function");  
   }  
}  
```  
  
 L'exemple suivant consomme le .dll et passe le handle délégué à la fonction native qui attend un pointeur fonction.  
  
```  
// delegate_to_native_function_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
delegate void Del(String ^s);  
public ref class A {  
public:  
   void delMember(String ^s) {  
      Console::WriteLine(s);  
   }  
};  
  
[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]  
extern "C" void nativeFunction(Del ^d);  
  
int main() {  
   A ^a = gcnew A;  
   Del ^d = gcnew Del(a, &A::delMember);  
   nativeFunction(d);   // Call to native function  
}  
```  
  
 **Sortie**  
  
  **Appel de fonction managée**   
## Associer des délégués à des fonctions non managées  
 Pour associer un délégué à une fonction native, vous devez inclure la fonction native dans un type managé et déclarer la fonction à appeler dans `PInvoke`.  
  
```  
// mcppv2_del_to_umnangd_func.cpp  
// compile with: /clr  
#pragma unmanaged  
extern "C" void printf(const char*, ...);  
class A {  
public:  
   static void func(char* s) {  
      printf(s);  
   }  
};  
  
#pragma managed  
public delegate void func(char*);   
  
ref class B {  
   A* ap;  
  
public:  
   B(A* ap):ap(ap) {}  
   void func(char* s) {  
      ap->func(s);   
   }  
};  
  
int main() {  
   A* a = new A;  
   B^ b = gcnew B(a);  
   func^ f = gcnew func(b, &B::func);  
   f("hello");  
   delete a;  
}  
```  
  
 **Sortie**  
  
  **hello**   
## Pour utiliser les délégués indépendants  
 Vous pouvez utiliser un délégué indépendant pour transmettre une instance du type dont vous voulez appeler la fonction lorsque le délégué est appelé.  
  
 Les délégués indépendants sont particulièrement utiles si vous voulez parcourir les objets dans une collenction \(en utilisantdes mots clés [for each, in](../dotnet/for-each-in.md)\) et appeler une fonction membre sur chaque instance.  
  
 Voici comment déclarer, instancier, puis appeler les délégués liés et déliés :  
  
|Action|Délégués liés|Délégués indépendants|  
|------------|-------------------|---------------------------|  
|Declare|La signature du délégué doit correspondre à la signature de la fonction que vous souhaitez appeler via le délégué.|Le premier paramètre de la signature du délégué est le type de `this` de l'objet que vous souhaitez appeler.<br /><br /> Après le premier paramètre, la signature du commercial doit correspondre à la signature de la fonction que vous souhaitez appeler via le délégué.|  
|instancier|Lorsque vous instanciez un délégué lié, spécifiez une fonction d'instance, ou un agrégat ou une fonction membre statique.<br /><br /> Pour spécifier une fonction d'instance, le premier paramètre est une instance du type dont vous voulez appeler la fonction membre et le deuxième paramètre représente l'adresse de la fonction que vous souhaitez appeler.<br /><br /> Si vous souhaitez appeler une fonction membre globale ou statique, passez simplement le nom d'une fonction globale ou de la fonction membre statique.|Lorsque vous instanciez un délégué indépendant, passez à l'adresse de la fonction que vous souhaitez appeler.|  
|Call|Lorsque vous appelez un délégué lié, passez uniquement les paramètres requis par la signature du délégué.|Comme pour un délégué lié, mais rappelez vous que le premier paramètre doit être une instance de l'objet qui contient la fonction à appeler.|  
  
 Cet exemple montre comment déclarer, instancier et appeler des délégués indépendants :  
  
```  
// unbound_delegates.cpp  
// compile with: /clr  
ref struct A {  
   A(){}  
   A(int i) : m_i(i) {}  
   void Print(int i) { System::Console::WriteLine(m_i + i);}  
  
private:  
   int m_i;  
};  
  
value struct V {  
   void Print() { System::Console::WriteLine(m_i);}  
   int m_i;  
};  
  
delegate void Delegate1(A^, int i);  
delegate void Delegate2(A%, int i);  
  
delegate void Delegate3(interior_ptr<V>);  
delegate void Delegate4(V%);  
  
delegate void Delegate5(int i);  
delegate void Delegate6();  
  
int main() {  
   A^ a1 = gcnew A(1);  
   A% a2 = *gcnew A(2);  
  
   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);  
   // delegate takes a handle  
   Unbound_Delegate1(a1, 1);  
   Unbound_Delegate1(%a2, 1);  
  
   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);  
   // delegate takes a tracking reference (must deference the handle)  
   Unbound_Delegate2(*a1, 1);  
   Unbound_Delegate2(a2, 1);  
  
   // instantiate a bound delegate to an instance member function  
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);  
   Bound_Del(1);  
  
   // instantiate value types  
   V v1 = {7};  
   V v2 = {8};  
  
   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);  
   Unbound_Delegate3(&v1);  
   Unbound_Delegate3(&v2);  
  
   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);  
   Unbound_Delegate4(v1);  
   Unbound_Delegate4(v2);  
  
   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);  
   Bound_Delegate3();  
}  
```  
  
 **Sortie**  
  
  **2**  
**3**  
**2**  
**3**  
**2**  
**7**  
**8**  
**7**  
**8**  
**7** L'exemple suivant montre comment utiliser les délégués entiers et les mots clés de [for each, in](../dotnet/for-each-in.md) pour parcourir les objets dans une collection et pour appeler une fonction membre sur chaque instance.  
  
```  
// unbound_delegates_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref class RefClass {  
   String^ _Str;  
  
public:  
   RefClass( String^ str ) : _Str( str ) {}  
   void Print() { Console::Write( _Str ); }  
};  
  
delegate void PrintDelegate( RefClass^ );  
  
int main() {  
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );  
  
   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );  
  
   for ( int i = 0; i < a->Length; ++i )  
      a[i] = gcnew RefClass( i.ToString() );  
  
   for each ( RefClass^ R in a )  
      d( R );  
  
   Console::WriteLine();  
}  
```  
  
 Cet exemple crée un délégué indépendant pour des fonctions de l'accesseur d'une propriété :  
  
```  
// unbound_delegates_3.cpp  
// compile with: /clr  
ref struct B {  
   property int P1 {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
  
private:  
   int m_i;  
};  
  
delegate void DelBSet(B^, int);  
delegate int DelBGet(B^);  
  
int main() {  
   B^ b = gcnew B;  
  
   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);  
   delBSet(b, 11);  
  
   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);     
   System::Console::WriteLine(delBGet(b));  
}  
```  
  
 **Sortie**  
  
  **11** L'exemple suivant indique comment appeler un délégué multicast, où une instance est liée et une instance est déliée.  
  
```  
// unbound_delegates_4.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int i) : m_i(i) {}  
  
   void f(R ^ r) {  
      System::Console::WriteLine("in f(R ^ r)");  
   }  
  
   void f() {  
      System::Console::WriteLine("in f()");  
   }  
  
private:  
   int m_i;  
};  
  
delegate void Del(R ^);  
  
int main() {  
   R ^r1 = gcnew R(11);  
   R ^r2 = gcnew R(12);  
  
   Del^ d = gcnew Del(r1, &R::f);  
   d += gcnew Del(&R::f);  
   d(r2);  
};  
```  
  
 **Sortie**  
  
  **in f\(R ^ r\)**  
**in f\(\)** L'exemple suivant montre comment créer et appeler un délégué générique indépendant.  
  
```  
// unbound_delegates_5.cpp  
// compile with: /clr  
ref struct R {  
   R(int i) : m_i(i) {}  
  
   int f(R ^) { return 999; }  
   int f() { return m_i + 5; }  
  
   int m_i;  
};  
  
value struct V {  
   int f(V%) { return 999; }  
   int f() { return m_i + 5; }   
  
   int m_i;  
};  
  
generic <typename T>  
delegate int Del(T t);  
  
generic <typename T>  
delegate int DelV(T% t);  
  
int main() {     
   R^ hr = gcnew R(7);  
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));  
  
   V v;  
   v.m_i = 9;  
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );  
}  
```  
  
 **Sortie**  
  
  **12**  
**14**   
## Voir aussi  
 [délégué](../windows/delegate-cpp-component-extensions.md)