---
title: "Erreur du compilateur C3769 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3769"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3769"
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3769
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe imbriquée ne peut pas avoir le même nom que la classe immédiatement englobante  
  
 Une classe imbriquée ne peut pas porter le même nom que la classe immédiatement englobante  
  
## Exemple  
 L'exemple suivant génère l'erreur C3769 :  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```