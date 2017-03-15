---
title: "Avertissement du compilateur (niveau&#160;3) C4646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4646"
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;3) C4646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la fonction déclarée avec \_\_declspec\(noreturn\) a un type de retour non void  
  
 Une fonction marquée avec le modificateur `__declspec`[noreturn](../../cpp/noreturn.md) doit avoir un type de retour [void](../../cpp/void-cpp.md).  
  
 L’exemple suivant génère l’avertissement C4646 :  
  
```  
// C4646.cpp // compile with: /W3 /WX int __declspec(noreturn) TestFunction() {   // C4646  make return type void }  
```