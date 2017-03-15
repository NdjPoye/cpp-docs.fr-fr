---
title: "Erreur du compilateur C3007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3007"
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : un argument est refusé dans la clause de la directive 'directive' OpenMP  
  
 Une directive OpenMP avait un argument, mais la directive refuse les arguments.  
  
 L’exemple suivant génère l’erreur C3007 :  
  
```  
// C3007.c // compile with: /openmp int main() { #pragma omp parallel for ordered(2)   // C3007 }  
```