---
title: "new (new slot in vtable)  (C++ Component Extensions) | Microsoft Docs"
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
  - "new keyword [C++]"
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new (new slot in vtable)  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `new` indique qu'un membre virtuel obtiendra un nouvel emplacement dans la vtable.  
  
> [!NOTE]
>  Le mot clé `new` a de nombreux usages et significations.  Pour plus d’informations, voir la rubrique d'homonymes  [new](../misc/new.md).  
  
## Tous les runtimes  
 \(Aucune note de cette fonctionnalité de langage ne s'applique à tous les runtimes.\)  
  
## Windows Runtime  
 Non pris en charge dans [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Remarques**  
  
 Dans une compilation **\/clr**, `new` indique qu'un membre virtuel obtiendra un nouvel emplacement dans la vtable et que la fonction ne substitue pas de méthode de classe de base.  
  
 `new`cause l'ajout du modificateur newslot à l'IL pour la fonction.  Pour plus d'informations sur newslot, consultez :  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="e9bb59a12f97840a5c3173bb77c6b5b1" class\="tgtSentence"\>Méthode MethodInfo.GetBaseDefinition\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [\<caps:sentence id\="tgt12" sentenceid\="f6ceddd85a425f38e7ed06e94a9808a9" class\="tgtSentence"\>Énumération de MethodAttributes\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### Configuration requise  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant montre les effets de `new`.  
  
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
  
  **C::f\(\) appelé**  
 **D::f\(\) appelé**  
 **D::g\(\) appelé**  
 **D::g\(\) appelé**  
 **E::f\(\) appelé**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Spécificateurs de substitution](../windows/override-specifiers-cpp-component-extensions.md)