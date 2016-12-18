---
title: "Avertissement du compilateur (niveau&#160;1) C4602 | Microsoft Docs"
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
  - "C4602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4602"
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pop\_macro : '\<nom\_macro\>' pas de \#pragma push\_macro défini au préalable pour cet identificateur  
  
 Si vous utilisez [pop\_macro](../../preprocessor/pop-macro.md) pour une macro particulière, vous devez au préalable passer le nom de cette macro à [push\_macro](../../preprocessor/push-macro.md). L’exemple suivant génère l’avertissement C4602 :  
  
```  
// C4602.cpp // compile with: /W1 int main() { #pragma pop_macro("x")   // C4602 x is not on the stack }  
```