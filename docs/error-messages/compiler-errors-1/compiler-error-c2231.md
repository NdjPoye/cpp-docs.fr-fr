---
title: "Erreur du compilateur C2231 | Microsoft Docs"
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
  - "C2231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2231"
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'.' : l’opérande de gauche pointe vers 'class\-key' ; utilisez '–\>'  
  
 L’opérande à gauche de l’opération de sélection de membres \(.\) est un pointeur au lieu d’une classe, d’une structure ou d’une union.  
  
 L’exemple suivant génère l’erreur C2231 :  
  
```  
// C2231.c struct S { int member; } s, *ps = &s; int main() { ps.member = 0;   // C2231 // OK ps->member = 0;   // crash s.member = 0; }  
```