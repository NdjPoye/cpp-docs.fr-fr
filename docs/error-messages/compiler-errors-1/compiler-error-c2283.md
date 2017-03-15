---
title: "Erreur du compilateur C2283 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2283"
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : spécificateur pure ou spécificateur de substitution abstrait non autorisé sur un struct sans nom  
  
 Une fonction membre d’une classe ou d’une structure sans nom est déclarée avec un spécificateur pure, ce qui n’est pas autorisé.  
  
 L’exemple suivant génère l’erreur C2283 :  
  
```  
// C2283.cpp // compile with: /c struct { virtual void func() = 0;   // C2283 }; struct T { virtual void func() = 0;   // OK };  
```