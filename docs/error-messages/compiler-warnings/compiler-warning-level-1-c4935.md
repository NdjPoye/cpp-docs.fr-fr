---
title: "Avertissement du compilateur (niveau&#160;1) C4935 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4935"
ms.assetid: a36c56d3-571a-44dd-bb0f-bcc6b020e134
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau&#160;1) C4935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécificateur d’accès à l’assembly modifié à partir de 'accès'  
  
 La visibilité d’assembly d’un type a été modifiée. Le compilateur utilise le dernier spécificateur qu’il trouve. Par exemple, la visibilité d’assembly d’une déclaration anticipée peut être différente de la visibilité d’assembly de la définition de classe.  
  
 L’erreur C4935 ne se produit que si vous utilisez **\/clr:oldSyntax**.  
  
 L’exemple suivant génère l’avertissement C4935 :  
  
```  
// C4935.cpp // compile with: /clr:oldSyntax /W1 /c public __gc public class X {   // C4935 int i; };  
```