---
title: "interface class  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "interface_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interface class keyword"
  - "interface struct keyword"
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: 30
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interface class  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare une interface.  Pour plus d'informations sur les interfaces natives, consultez [\_\_interface](../cpp/interface.md).  
  
## Tous les runtimes  
 **Syntaxe**  
  
```  
  
        interface_access interface class  name :  inherit_access base_interface {};  
interface_access interface struct name :  inherit_access base_interface {};  
```  
  
 **Paramètres**  
  
 *interface\_access*  
 L'accessibilité d'une interface à l'extérieur de l'assembly.  Les valeurs possibles sont **public** et `private`.  `private` est la valeur par défaut.  Les interfaces imbriquées ne peuvent pas avoir un identificateur *interface\_access*.  
  
 *name*  
 Nom de l'interface.  
  
 *inherit\_access*  
 L'accessibilité de *base\_interface*.  La seule accessibilité autorisée pour une interface de base est `public` \(par défaut\).  
  
 *base\_interface* \(facultatif\)  
 Interface de base pour l'interface *name*.  
  
 **Remarques**  
  
 **interface struct** équivaut à **interface class**.  
  
 Un interface peut contenir des déclarations pour les fonctions, les événements, et les propriétés.  Tous les membres de l'interface ont l'accessibilité publique.  Un interface peut également contenir des membres de données statiques, des fonctions, des événements, et des propriétés, et ces membres statiques doivent être définis dans l'interface.  
  
 Un interface définit la manière dont une classe peut être implémentée.  Un interface n'est pas une classe et les classes peuvent uniquement implémenter les interfaces.  Lorsqu'une classe définit une fonction déclarée dans une interface, la fonction est implémentée, pas remplacée.  Par conséquent, la recherche du nom n'inclut pas les membres de l'interface.  
  
 Une classe ou struct hérité d'une interface doit implémenter tous les membres de l'interface.  En implémentant l'interface *nom* vous devez également implémenter les interfaces de `base_interface` liste.  
  
 Pour plus d'informations, consultez :  
  
-   [Constructeur d'Interface Statique](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Generic Interfaces \(Visual C\+\+\)](../windows/generic-interfaces-visual-cpp.md)  
  
 Pour plus d'informations sur d'autres types CLR, consultez [Classes et structs](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Vous pouvez détecter au moment de la compilation si un type est une interface avec `__is_interface_class(``type``)`.  Pour plus d'informations, consultez [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Dans l'environnement de développement, vous pouvez obtenir de l'aide F1 sur ces mots clés en mettant en surbrillance le mot clé, \(`interface class`, par exemple\) et en appuyant sur F1.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Remarques**  
  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Windows Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Remarques**  
  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Common Language Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant montre comment une interface peut définir le comportement d'une fonction d'horloge.  
  
```  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **Sortie**  
  
  **in Function\_3**  
 **in Function\_2**  
 **in Function\_1**  
 **8**  
 **OnClick: 7, 3.14159**  
 **in Function\_1** **Exemple**  
  
 Affiche l'exemple de code suivant deux manières d'implémenter des fonctions avec la même signature déclarés dans plusieurs interfaces et où ces interfaces sont utilisées par une classe.  
  
```  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)