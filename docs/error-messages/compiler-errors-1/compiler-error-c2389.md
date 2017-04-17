---
title: "Erreur du compilateur C2389 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2389"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2389"
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2389
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : opérande 'nullptr' non conforme  
  
 `nullptr` ne peut pas être un opérande.  
  
 L’exemple suivant génère l’erreur C2389 :  
  
```  
// C2389.cpp // compile with: /clr int main() { throw nullptr;   // C2389 }  
```