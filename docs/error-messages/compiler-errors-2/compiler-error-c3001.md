---
title: "Erreur du compilateur C3001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3001"
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'texte\_erreur' : nom de directive OpenMP attendu  
  
 Le pragma `omp` doit être suivi d’une directive.  
  
 L’exemple suivant génère l’erreur C3001 :  
  
```  
// C3001.c // compile with: /openmp int main() { #pragma omp   // C3001 missing token }  
```