---
title: Erreur du compilateur C2259 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2259
dev_langs:
- C++
helpviewer_keywords:
- C2259
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0837d8f5e48ccf0de0ba8630801667da2ddb6bfa
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2259"></a>Erreur du compilateur C2259
'classe' : ne peut pas instancier une classe abstraite  
  
 Code déclare une instance d’une structure ou une classe abstraite.  
  
 Vous ne pouvez pas instancier une classe ou une structure avec une ou plusieurs fonctions virtuelles pures. Pour instancier des objets d’une classe dérivée, la classe dérivée doit substituer chaque fonction virtuelle pure.  
  
 Pour plus d’informations, consultez [classes implicitement abstraites](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes).  
  
 L’exemple suivant génère l’erreur C2259 :  
  
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
  
 Chaque fois que vous dérivez d’une interface et implémentez les méthodes d’interface dans la classe dérivée avec des autorisations d’accès autre que public, vous pouvez recevoir l’erreur C2259.  Cela se produit, car le compilateur attend les méthodes d’interface implémentées dans la classe dérivée doit avoir un accès public. Lorsque vous implémentez les fonctions membres d’une interface avec des autorisations d’accès plus restrictives, le compilateur ne considère pas les implémentations des méthodes d’interface définies dans l’interface, qui à son tour la classe dérivée une classe abstraite.  
  
 Il existe deux manières de contourner le problème :  
  
-   Vérifiez les autorisations d’accès public pour les méthodes implémentées.  
  
-   Utilisez l’opérateur de résolution de portée pour les méthodes d’interface implémentées dans la classe dérivée pour qualifier le nom de la méthode implémentée par le nom de l’interface.  
  
 L’erreur C2259 peut également se produire suite à la mise en conformité réalisée dans Visual C++ 2005, **/Zc :** est désormais activé par défaut. Dans ce cas, l’erreur C2599 peut être résolue en compilant avec **/Zc:wchar_t-**, afin d’obtenir le comportement des versions précédentes, ou de préférence en mettant à jour vos types afin qu’ils soient compatibles. Pour plus d’informations, consultez [/Zc:wchar_t (wchar_t est un type natif)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
 L’exemple suivant génère l’erreur C2259 :  
  
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
  
 L’exemple suivant génère l’erreur C2259 :  
  
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

