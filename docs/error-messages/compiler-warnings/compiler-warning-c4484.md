---
title: "Avertissement du compilateur C4484 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4484"
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_substitution' : correspond à la méthode de classe ref de base 'fonction\_classe\_base', mais n'est pas marqué comme 'virtual', 'new' ou 'override' ; 'new' \(et non 'virtual'\) est pris en compte par défaut  
  
 Lors de la compilation avec **\/clr**, le compilateur ne substitue pas implicitement une fonction de classe de base, ce qui signifie que la fonction aura un nouvel emplacement dans vtable.  Pour remédier à cela, spécifiez explicitement si une fonction est une substitution.  
  
 Pour plus d'informations, consultez :  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 est toujours émis en tant qu'erreur.  Utilisez le pragma [warning](../../preprocessor/warning.md) pour supprimer l'erreur C4484.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4484 :  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```