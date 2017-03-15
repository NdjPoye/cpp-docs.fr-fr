---
title: "Avertissement du compilateur (niveau&#160;4) C4918 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4918"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4918"
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;4) C4918
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' : caractère non valide dans la liste d’optimisation pragma  
  
 Un caractère inconnu a été trouvé dans la liste d’optimisation d’une instruction pragma [optimize](../../preprocessor/optimize.md).  
  
 Par exemple, l’instruction suivante génère l’avertissement C4918 :  
  
```  
// C4918.cpp // compile with: /W4 #pragma optimize("X", on) // C4918 expected int main() { }  
```