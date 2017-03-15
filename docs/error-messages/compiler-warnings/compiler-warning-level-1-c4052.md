---
title: "Avertissement du compilateur (niveau&#160;1) C4052 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4052"
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

déclarations de fonction différentes, une seule contient des arguments de variables  
  
 L’une des déclarations de la fonction ne contient pas d’arguments de variables. Elle est ignorée.  
  
 L’exemple suivant génère l’avertissement C4052 :  
  
```  
// C4052.c // compile with: /W4 /c int f(); int f(int i, ...);   // C4052  
```