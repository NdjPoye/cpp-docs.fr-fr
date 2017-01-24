---
title: "Erreur du compilateur C2334 | Microsoft Docs"
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
  - "C2334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2334"
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jetons inattendus avant ': ou {' ; corps apparent de la fonction ignoré  
  
 L'exemple suivant génère l'erreur C2334.  Cette erreur se produit après l'erreur C2059 :  
  
```  
// C2334.cpp  
// compile with: /c  
// C2059 expected  
struct s1 {  
   s1   {}   // C2334  
   s1() {}   // OK  
};  
```