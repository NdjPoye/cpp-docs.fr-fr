---
title: "Erreur du compilateur C3380 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3380"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3380"
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3380
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : spécificateur d’accès à l’assembly non valide \- seuls 'public' ou 'private' sont autorisés  
  
 En cas d’application à une classe managée ou à une structure, les mots clés [public](../../cpp/public-cpp.md) et [private](../../cpp/private-cpp.md) indiquent si la classe doit être exposée dans les métadonnées de l’assembly. Seuls `public` ou `private` peuvent être appliqués à une classe contenue dans un programme compilé avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Quand les mots clés `ref` et `value` sont utilisés avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md), ils indiquent qu’une classe est managée \(consultez [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)\).  
  
 L’exemple suivant génère l’erreur C3380 :  
  
```  
// C3380_2.cpp // compile with: /clr protected ref class A {   // C3380 // try the following line instead // ref class A { public: static int i = 9; }; int main() { A^ myA = gcnew A; System::Console::WriteLine(myA->i); }  
```  
  
 L’exemple suivant génère l’erreur C3380 :  
  
```  
// C3380.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> protected __gc class A {   // C3380 // try the following line instead // __gc class A { public: static int i = 9; }; int main() { A *myA = new A; Console::WriteLine(myA->i); }  
```