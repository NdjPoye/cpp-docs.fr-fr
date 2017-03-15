---
title: Erreur du compilateur C3767 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3767
dev_langs:
- C++
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
caps.latest.revision: 12
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
ms.openlocfilehash: b0cce511d895aae218c1b2ab04d129173b049983
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3767"></a>Erreur du compilateur C3767
fonctions de candidat 'fonction' n’est pas accessibles  
  
 Une fonction friend définie dans une classe n’est pas supposé être traitée comme si elle était définie et déclarée dans la portée espace de noms global. Il peut, toutefois, être trouvée par une recherche dépendante de l’argument.  
  
 L’erreur C3767 peut également être provoqué par une modification avec rupture : les types natifs sont désormais privés par défaut dans un **/clr** compilation ; consultez [tapez visibilité](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3767 :  
  
```  
// C3767a.cpp  
// compile with: /clr  
using namespace System;  
public delegate void TestDel();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;  
};  
  
public ref class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass^ patient = gcnew MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass^ x = gcnew MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2^ y = gcnew MyClass2();  
   y->Test();  
};  
```  
  
 L’exemple suivant génère l’erreur C3767 :  
  
```  
// C3767c.cpp  
// compile with: /clr /c  
  
ref class Base  {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
ref class Der : public Base {  
   void Method() {  
      ((Base^)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 Dans Visual C++ .NET 2002, le compilateur a modifié le mode de que recherche des symboles. Dans certains cas, il recherchait automatiquement des symboles dans un espace de noms spécifié. Maintenant, elle utilise la recherche dépendante de l’argument.  
  
 L’exemple suivant génère l’erreur C3767 :  
  
```  
// C3767e.cpp  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3767 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
 Pour le code qui est valide dans Visual C++ .NET 2003 et Visual C++ .NET 2002, déclarez la fonction friend dans la portée de la classe et définissez-la dans la portée espace de noms :  
  
```  
// C3767f.cpp  
class MyClass {  
   int m_private;  
   friend void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  
```
