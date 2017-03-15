---
title: "Erreur du compilateur C3253 | Microsoft Docs"
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
  - "C3253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3253"
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : erreur de substitution explicite  
  
 Une substitution explicite n'a pas été spécifiée correctement.  Par exemple, vous ne pouvez pas spécifier d'implémentation pour une substitution que vous spécifiez également comme pure.  Pour plus d'informations, consultez [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3253 :  
  
```  
// C3253.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
   void b();  
   void c();  
};  
  
public ref struct R : I {  
   virtual void a() = 0, I::a {}   // C3253  
   virtual void b() = I::a {}   // OK  
   virtual void c() = 0;   // OK  
};  
```