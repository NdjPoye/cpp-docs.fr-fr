---
title: New (nouvel emplacement dans vtable) (Extensions du composant C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7189909f3cff84d2bb1a767e4ddeda817bcd6128
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="new-new-slot-in-vtable--c-component-extensions"></a>nouveau (nouvel emplacement dans vtable)  (extensions du composant C++)
Le `new` mot clé indique qu’un membre virtuel obtiendra un nouvel emplacement dans vtable.  
  
## <a name="all-runtimes"></a>Tous les runtimes  
 (Aucune remarque pour cette fonctionnalité de langage ne s’applique à tous les runtimes.)  
  
## <a name="windows-runtime"></a>Windows Runtime  
 Non pris en charge dans Windows Runtime.  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Remarques**  
  
 Dans un **/CLR** compilation, `new` indique qu’un membre virtuel obtiendra un nouvel emplacement dans vtable ; que la fonction ne remplace pas une méthode de classe de base.  
  
 `new` provoque le modificateur newslot à ajouter avec le langage intermédiaire pour la fonction.  Pour plus d’informations sur newslot, consultez :  
  
-   [MethodInfo.GetBaseDefinition (méthode)](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [Énumération MethodAttributes](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### <a name="requirements"></a>Spécifications  
 Option du compilateur : **/clr**  
  
### <a name="examples"></a>Exemples  
 **Exemple**  
  
 L’exemple suivant montre l’effet de `new`.  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Sortie**  
  
```Output  
C::f() called  
  
D::f() called  
  
D::g() called  
  
D::g() called  
  
E::f() called  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Extensions de composant pour les plateformes Runtime](../windows/component-extensions-for-runtime-platforms.md)   
 [Spécificateurs de substitution](../windows/override-specifiers-cpp-component-extensions.md)