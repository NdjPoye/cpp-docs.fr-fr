---
title: "Erreur du compilateur C2259 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2259"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2259"
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Erreur du compilateur C2259
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : impossible d'instancier une classe abstraite  
  
 Le code déclare une instance d'une classe ou d'une structure abstraite.  
  
 Vous ne pouvez pas instancier une classe ou une structure avec une ou plusieurs fonctions virtuelles \(virtual\) pure.  Pour instancier des objets d'une classe dérivée, celle\-ci doit substituer chaque fonction virtuelle pure.  
  
 Pour plus d'informations, consultez [Classes implicitement abstraites](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 L'exemple suivant génère l'erreur C2259 :  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 Chaque fois que vous dérivez d'une interface et implémentez les méthodes d'interface de la classe dérivée avec des autorisations d'accès autres que publiques, l'erreur C2259 peut se produire.  Cela est dû au fait que le compilateur s'attend à ce que les méthodes d'interface implémentées dans la classe dérivée disposent d'un accès public.  Lorsque vous implémentez les fonctions membres pour une interface disposant d'autorisations d'accès plus restrictives, le compilateur ne les considère pas comme des implémentations des méthodes d'interface définies dans l'interface qui font ensuite de la classe dérivée une classe abstraite.  
  
 Il existe deux solutions de contournement possibles pour le problème :  
  
-   Rendez publiques les autorisations d'accès des méthodes implémentées.  
  
-   Utilisez l'opérateur de résolution de portée pour les méthodes d'interface implémentées dans la classe dérivée afin de qualifier le nom de méthode implémenté avec le nom de l'interface.  
  
 L'erreur C2259 peut également être due à la mise en conformité pour Visual C\+\+ 2005, **\/Zc:wchar\_t** est désormais activé par défaut.  Dans cette situation, l'erreur C2599 peut être résolue en compilant avec **\/Zc:wchar\_t\-**, afin d'obtenir le comportement des versions antérieures, ou de préférence en mettant à jour vos types afin qu'ils soient compatibles.  Pour plus d'informations, consultez [\/Zc:wchar\_t \(wchar\_t est un type natif\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 L'exemple suivant génère l'erreur C2259 :  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 L'exemple suivant génère l'erreur C2259 :  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
  
 L'exemple suivant génère l'erreur C2259 :  
  
```  
// C2259d.cpp  
// compile with: /clr:oldSyntax  
public __gc __interface MyInterface {  
   void MyMethod();  
};  
  
__gc class MyDerivedClass : public MyInterface {  
// Uncomment the following line to resolve.  
// public:  
   void MyMethod() {};  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass *instance = new MyDerivedClass();   // C2259  
}  
```