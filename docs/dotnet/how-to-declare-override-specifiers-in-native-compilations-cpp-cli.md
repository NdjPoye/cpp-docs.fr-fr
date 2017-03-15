---
title: "Comment&#160;: d&#233;clarer des sp&#233;cificateurs de substitution dans les compilations natives (C++/CLI) | Microsoft Docs"
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
  - "spécificateurs de remplacement dans une compilation native, remplacer"
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;clarer des sp&#233;cificateurs de substitution dans les compilations natives (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[sceller](../windows/sealed-cpp-component-extensions.md), [résumer](../windows/abstract-cpp-component-extensions.md), et [substituter](../windows/override-cpp-component-extensions.md) sont disponibles dans les compilations qui n'utilisent pas **\/ZW** ou [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  La langue norme ISO C\+\+11 a l'identification de [substitution](../cpp/override-specifier.md) et l'identification d' [édition intégrale](../cpp/final-specifier.md), et les deux sont pris en charge dans l'utilisateur Visual Studio `final` au lieu de `sealed` dans le code qui est destiné à être compilé comme étant réservé au format natif.  
  
## Exemple  
  
### Description  
 L'exemple suivant indique que `sealed` est valide dans des compilations natives.  
  
### Code  
  
```  
// sealed_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
   virtual void g();  
};  
  
class X : public I1 {  
public:  
   virtual void g() sealed {}  
};  
  
class Y : public X {  
public:  
  
   // the following override generates a compiler error  
   virtual void g() {}   // C3248 X::g is sealed!  
};  
```  
  
## Exemple  
  
### Description  
 Le prochain exemple indique que `override` est valide dans des compilations natives.  
  
### Code  
  
```  
// override_native_keyword.cpp  
#include <stdio.h>  
__interface I1 {  
   virtual void f();  
};  
  
class X : public I1 {  
public:  
   virtual void f() override {}   // OK  
   virtual void g() override {}   // C3668 I1::g does not exist  
};  
```  
  
## Exemple  
  
### Description  
 Cet exemple indique que `abstract` est valide dans des compilations natives.  
  
### Code  
  
```  
// abstract_native_keyword.cpp  
class X abstract {};  
  
int main() {  
   X * MyX = new X;   // C3622 cannot instantiate abstract class  
}  
```  
  
## Voir aussi  
 [Spécificateurs de substitution](../windows/override-specifiers-cpp-component-extensions.md)