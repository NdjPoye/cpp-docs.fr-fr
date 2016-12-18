---
title: "Erreur du compilateur C3016 | Microsoft Docs"
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
  - "C3016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3026"
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : la variable d’index de l’instruction 'for' OpenMP doit disposer d’un type intégral signé  
  
 La variable d’index dans une instruction `for` OpenMP doit être un type intégral signé.  
  
 L’exemple suivant génère l’erreur C3016 :  
  
```  
// C3016.cpp // compile with: /openmp int main() { #pragma omp parallel { unsigned int i = 0; // Try the following line instead: // int i = 0; #pragma omp for for (i = 0; i <= 10; ++i)   // C3016 { } } }  
```