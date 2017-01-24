---
title: "Avertissement du compilateur (niveau 4) C4481 | Microsoft Docs"
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
  - "C4481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4481"
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : spécificateur de substitution 'MotClé'  
  
 Vous avez utilisé un mot clé qui ne figure pas dans la norme C\+\+ \(par exemple, l'un des spécificateurs de substitution qui fonctionnent également sous \/clr\).  Pour plus d'informations, consultez  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Spécificateurs de substitution](../../windows/override-specifiers-cpp-component-extensions.md)  
  
## Exemple  
 L'exemple suivant génère l'erreur C4481 :  
  
```  
// C4481.cpp  
// compile with: /W4 /c  
class B {  
   virtual void f(unsigned);  
};  
  
class C : B {  
   void f(unsigned) override;   // C4481  
   void f2(unsigned);  
};  
```