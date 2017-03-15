---
title: "Erreur du compilateur C2377 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2377"
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : redéfinition ; un typedef ne peut pas être surchargé avec un autre symbole  
  
 Un identificateur `typedef` est redéfini.  
  
 L’exemple suivant génère l’erreur C2377 :  
  
```  
// C2377.cpp // compile with: /c typedef int i; int i;   // C2377 int j;   // OK  
```