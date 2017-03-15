---
title: "Erreur du compilateur C3055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3055"
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : impossible de référencer le symbole avant qu’il ne soit utilisé dans la directive 'threadprivate'  
  
 Un symbole a été référencé puis utilisé dans une clause [threadprivate](../../parallel/openmp/reference/threadprivate.md), ce qui n’est pas autorisé.  
  
 L’exemple suivant génère l’erreur C3055 :  
  
```  
// C3055.cpp // compile with: /openmp int x, y; int z = x; #pragma omp threadprivate(x, y)   // C3055 void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 Résolution possible :  
  
```  
// C3055b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```