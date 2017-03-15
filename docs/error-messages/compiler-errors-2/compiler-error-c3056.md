---
title: "Erreur du compilateur C3056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3056"
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : le symbole n’est pas dans la même portée avec la directive 'threadprivate'  
  
 Un symbole utilisé dans une clause [threadprivate](../../parallel/openmp/reference/threadprivate.md) doit être dans la même portée que la clause `threadprivate`.  
  
 L’exemple suivant génère l’erreur C3056 :  
  
```  
// C3056.cpp // compile with: /openmp int x, y; void test() { #pragma omp threadprivate(x, y)   // C3056 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 Résolution possible :  
  
```  
// C3056b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```