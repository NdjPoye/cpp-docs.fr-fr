---
title: "Explicit Overrides  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overriding, override [C++]"
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Explicit Overrides  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment remplacer explicitement un membre d'une classe de base ou d'une interface.  Une substitution \(explicite\) nommée doit être utilisée pour remplacer une méthode et une méthode dérivée qui porte un nom différent.  
  
## Tous les runtimes  
 **Syntaxe**  
  
```  
  
        overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **Paramètres**  
  
 *overriding\-function\-declarator*  
 Le type de retour, le nom, et la liste des arguments de la fonction substituante.  Notez que la fonction substituante ne doit pas avoir le même nom que la fonction qui est remplacée.  
  
 *type*  
 Le type de base qui contient une fonction à remplacer.  
  
 *function*  
 Une liste séparée par des virgules d'un ou plusieurs noms de fonctions à remplacer.  
  
 *overriding\-function\-definition*  
 Les instructions de corps de la fonction qui définissent la fonction substituante.  
  
 **Remarques**  
  
 Substitutions explicites pour créer un alias pour une signature de méthode, ou pour fournir différentes implémentations pour les méthodes avec la même signature.  
  
 Pour plus d'informations sur la modification du comportement des types hérités et les membres de type hérités, consultez [Spécificateurs de substitution](../windows/override-specifiers-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Remarques**  
  
 Pour plus d'informations sur les substitutions explicites en code natif ou le code compilé avec **\/clr:oldSyntax**, consultez [Substitutions explicites](../cpp/explicit-overrides-cpp.md).  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant montre une substitution et une implémentation simple et implicites d'un membre dans une interface de base, pas avec les substitutions explicites.  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **Sortie**  
  
  **X::f override of I1::f** **Exemple**  
  
 L'exemple de code suivant montre comment implémenter tous les membres d'interface avec une signature commune, dans la syntaxe de priorité explicite.  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **Sortie**  
  
  **Substitution de X::f d'I1::f et d'I2::f**  
 **Substitution de X::f d'I1::f et d'I2::f** **Exemple**  
  
 L'exemple de code suivant montre comment une substitution de fonction peut avoir un autre nom que la fonction qu'il implémente.  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **Sortie**  
  
  **X::g** **Exemple**  
  
 L'exemple de code suivant montre une implémentation d'interface explicites qui implémente une collection de sûr de type.  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)