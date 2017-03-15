---
title: "Erreur du compilateur C2624 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2624"
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les classes locales ne peuvent pas être utilisées pour déclarer des variables 'extern'  
  
 Une classe ou une structure locale ne peut pas être utilisée pour déclarer des variables `extern`.  
  
 L'exemple suivant génère l'erreur C2624 :  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```