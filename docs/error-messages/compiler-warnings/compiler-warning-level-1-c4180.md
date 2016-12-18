---
title: "Avertissement du compilateur (niveau&#160;1) C4180 | Microsoft Docs"
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
  - "C4180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4180"
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

qualificateur appliqué au type fonction n'a pas de sens ; ignoré  
  
 Un qualificateur, tel que **const**, est appliqué à un type de fonction défini par `typedef`.  
  
## Exemple  
  
```  
// C4180.cpp // compile with: /W1 /c typedef int FuncType(void); // the const qualifier cannot be applied to the // function type FuncType const FuncType f;   // C4180  
```