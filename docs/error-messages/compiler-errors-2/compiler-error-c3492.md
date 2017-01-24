---
title: "Erreur du compilateur C3492 | Microsoft Docs"
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
  - "C3492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3492"
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : vous ne pouvez pas capturer un membre d’union anonyme  
  
 Vous ne pouvez pas capturer un membre d’une union sans nom.  
  
### Pour corriger cette erreur  
  
-   Donnez un nom à l’union et passez la structure d’union complète à la liste de capture de l’expression lambda.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3492, car il capture un membre d’une union anonyme :  
  
```  
// C3492a.cpp int main() { union { char ch; int x; }; ch = 'y'; [&x](char ch) { x = ch; }(ch); // C3492 }  
```  
  
## Exemple  
 L’exemple suivant résout l’erreur C3492 en nommant l’union et en passant la structure d’union complète à la liste de capture de l’expression lambda :  
  
```  
// C3492b.cpp int main() { union { char ch; int x; } u; u.ch = 'y'; [&u](char ch) { u.x = ch; }(u.ch); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)