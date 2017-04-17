---
title: "Avertissement du compilateur (niveau&#160;1) C4185 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4185"
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau&#160;1) C4185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

attribut \#import inconnu 'attribute' ignoré  
  
 L’attribut n’est pas un attribut valide de `#import`. Elle est ignorée.  
  
## Exemple  
  
```  
// C4185.cpp // compile with: /W1 /c #import "stdole2.tlb" no_such_attribute   // C4185  
```