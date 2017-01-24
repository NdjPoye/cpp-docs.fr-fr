---
title: "Avertissement du compilateur C4485 | Microsoft Docs"
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
  - "C4485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4485"
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction\_substitution' : correspond à la méthode de classe ref de base 'fonction\_classe\_base', mais n'est pas marqué comme 'new' ou 'override' ; 'new' \(et 'virtual'\) est pris par défaut  
  
 Un accesseur substitue, avec ou sans le mot clé `virtual`, une fonction d'accesseur de classe de base, mais le spécificateur `override` ou `new` ne faisait pas partie de la signature de la fonction de substitution.  Ajoutez le spécificateur `new` ou `override` pour résoudre cet avertissement.  
  
 Pour plus d'informations, consultez [override](../../windows/override-cpp-component-extensions.md) et [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
 C4485 est toujours émis en tant qu'erreur.  Utilisez le pragma [warning](../../preprocessor/warning.md) pour supprimer l'erreur C4485.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4485 :  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```