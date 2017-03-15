---
title: "Erreur du compilateur C3005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3005"
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'error\_text' : jeton inattendu rencontré dans la directive 'directive' OpenMP  
  
 Une directive OpenMP est incorrecte.  
  
 L’exemple suivant génère l’erreur C3005 :  
  
```  
// C3005.c // compile with: /openmp int main() { #pragma omp parallel + for   // C3005 }  
```  
  
 L’erreur C3005 peut également se produire si vous insérez une accolade ouvrante sur la même ligne que le pragma.  
  
```  
// C3005b.c // compile with: /openmp int main() { #pragma omp parallel {   // C3005 put open brace on next line lbl2:; } goto lbl2; }  
```