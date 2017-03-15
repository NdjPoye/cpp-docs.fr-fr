---
title: "Erreur du compilateur C2344 | Microsoft Docs"
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
  - "C2344"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2344"
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2344
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

align\(\#\) : l’alignement doit être une puissance de deux  
  
 Quand vous utilisez le mot clé [align](../../cpp/align-cpp.md), la valeur que vous passez doit être une puissance de deux.  
  
 Par exemple, le code suivant génère l’erreur C2344, car 3 n’est pas une puissance de deux :  
  
```  
// C2344.cpp // compile with: /c __declspec(align(3)) int a;   // C2344 __declspec(align(4)) int b;   // OK  
```