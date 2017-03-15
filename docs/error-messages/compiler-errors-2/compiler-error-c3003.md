---
title: "Erreur du compilateur C3003 | Microsoft Docs"
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
  - "C3003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3003"
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'directive' : nom de directive OpenMP non autorisé après des clauses de directive  
  
 Un nom de directive OpenMP ne peut pas suivre une clause de directive OpenMP.  
  
 L’exemple suivant génère l’erreur C3003 :  
  
```  
// C3003.c // compile with: /openmp int main() { int x, y, z; #pragma omp parallel shared(x, y, z) for   // C3003 }  
```