---
title: "Erreur du compilateur C3010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3010"
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'étiquette' : saut hors du bloc structuré OpenMP non autorisé  
  
 Le code ne peut pas sauter dans ou hors d’un bloc OpenMP.  
  
 L’exemple suivant génère l’erreur C3010 :  
  
```  
// C3010.c // compile with: /openmp int main() { #pragma omp parallel { #pragma omp parallel { goto lbl3; } } lbl3:;   // C3010 }  
```