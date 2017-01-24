---
title: "sealed  (C++ Component Extensions) | Microsoft Docs"
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
  - "sealed_cpp"
  - "sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed keyword [C++]"
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sealed  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sealed` est un mot clé contextuel pour les classes ref qui indique qu'un membre virtuel ne peut pas être remplacé ou qu'un type ne peut pas être utilisé comme type de base.  
  
> [!NOTE]
>  Le langage standard ISO C \+\+ 11 contient le mot clé [final](../cpp/final-specifier.md) qui est pris en charge dans Visual Studio.  Utilisez `final` sur les classes standard et `sealed` sur les classes ref.  
  
## Tous les runtimes  
 **Syntaxe**  
  
```  
  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
  
```  
  
 **Paramètres**  
  
 *identifier*  
 Nom de la fonction ou de la classe.  
  
 *return\-type*  
 Type retourné par une fonction.  
  
 **Notes**  
  
 Dans le premier exemple de syntaxe, une classe est sealed.  Dans le deuxième exemple, une fonction virtuelle est sealed.  
  
 Le mot clé `sealed` est valide pour les cibles natives et également pour [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et le Common Language Runtime \(CLR\).  Pour plus d'informations, voir [Spécificateurs de substitution et compilations natives](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Vous pouvez détecter au moment de la compilation si un type est sealed à l'aide de la caractéristique de type `__is_sealed (``type``)`.  Pour plus d'informations, voir [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` est un mot clé contextuel.  Pour plus d'informations, voir [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Voir [Classes et structures de référence \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Common Language Runtime.\)  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
### Exemples  
 L'exemple de code suivant montre l'effet de `sealed` sur un membre virtuel.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
 **Sortie**  
  
  **Substitution de X::f de I1::f**  
 **Substitution de X::f de I1::g**  
 **Substitution de Y::f de I1::f** L'exemple de code suivant montre comment marquer une classe comme sealed.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)