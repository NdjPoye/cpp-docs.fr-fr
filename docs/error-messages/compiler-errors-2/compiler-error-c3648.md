---
title: "Erreur du compilateur C3648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3648"
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cette syntaxe de substitution explicite requiert \/clr:oldSyntax  
  
 Lors d'une compilation pour la syntaxe managée la plus récente, le compilateur a détecté une syntaxe de substitution explicite pour des versions antérieures.  
  
 Pour plus d'informations, consultez [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  Pour plus d'informations sur l'ancienne syntaxe, consultez [Substitutions explicites](../../cpp/explicit-overrides-cpp.md).  
  
 L'exemple suivant génère l'erreur C3648 :  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```