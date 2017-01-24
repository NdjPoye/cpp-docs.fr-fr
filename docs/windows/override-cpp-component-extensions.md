---
title: "override  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "overriding, override keyword [C++]"
  - "override keyword [C++]"
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# override  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé contextuel `override` indique qu'un membre de type se substitue à une classe de base ou un membre d'interface de base.  
  
## Remarques  
 Le mot clé `override` est valide lors de la compilation pour les cibles natives \(option du compilateur par défaut\), les cibles Windows Runtime \(option du compilateur **\/ZW**\) ou les cibles Common Language Runtime \(option du compilateur **\/clr**\).  
  
 Pour plus d'informations sur les spécificateurs de substitution, consultez [Spécificateur de substitution](../cpp/override-specifier.md) et [Spécificateurs de substitution et compilations natives](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Pour plus d'informations sur les mots clés contextuels, consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Exemples  
 **Exemple**  
  
 L'exemple de code suivant montre qu'`override` peut également être utilisé dans les compilations natives.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Exemple**  
  
 L'exemple de code suivant montre qu'`override` peut être utilisé dans les compilations Windows Runtime.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Configuration requise**  
  
 Option du compilateur : **\/ZW**  
  
 **Exemple**  
  
 L'exemple de code suivant montre qu'`override` peut être utilisé dans les compilations Common Language Runtime.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Configuration requise**  
  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [Spécificateur de substitution](../cpp/override-specifier.md)   
 [Spécificateurs de substitution](../windows/override-specifiers-cpp-component-extensions.md)