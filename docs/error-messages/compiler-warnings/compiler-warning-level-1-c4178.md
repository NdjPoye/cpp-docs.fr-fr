---
title: "Avertissement du compilateur (niveau&#160;1) C4178 | Microsoft Docs"
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
  - "C4178"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4178"
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4178
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

constante case 'constant' trop grande pour le type de l’expression de switch  
  
 Une constante case dans une expression `switch` ne tient pas dans le type auquel elle est assignée.  
  
## Exemple  
  
```  
// C4178.cpp // compile with: /W1 int main() { int i;  // maximum size of unsigned long int is 4294967295 switch( i ) { case 4294967295:   // OK break; case 4294967296:   // C4178 break; } }  
```