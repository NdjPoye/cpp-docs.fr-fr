---
title: "Avertissement du compilateur (niveau&#160;1) C4678 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4678"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4678"
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement du compilateur (niveau&#160;1) C4678
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la classe de base 'base\_type' est moins accessible que 'derived\_type'  
  
 Un type public dérive d’un type privé. Si le type public est instancié dans un assembly référencé, les membres du type de base privé ne sont pas accessibles.  
  
 L’avertissement C4678 ne peut être atteint qu’avec **\/clr:oldSyntax**. C’est une erreur, en utilisant **\/clr**, d’avoir une classe de base qui est moins accessible que sa classe dérivée.  
  
 L’exemple suivant génère l’erreur C4678 :  
  
```  
// C4678.cpp // compile with: /clr:oldSyntax /LD /W1 #using <mscorlib.dll> private __gc struct privateG { // try the following line instead // public __gc struct privateG { public: int i; }; public __gc struct V: public privateG {   // C4678 public: int j; };  
```