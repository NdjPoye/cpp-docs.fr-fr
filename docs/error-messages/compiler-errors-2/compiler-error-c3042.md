---
title: "Erreur du compilateur C3042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3042"
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les clauses 'copyprivate' et 'nowait' ne peuvent pas figurer en même temps dans la directive 'directive' OpenMP  
  
 Les clauses [copyprivate](../../parallel/openmp/reference/copyprivate.md) et [nowait](../../parallel/openmp/reference/nowait.md) s’excluent mutuellement sur la directive spécifiée. Pour corriger cette erreur, supprimez l’une des clauses `copyprivate` ou `nowait` ou les deux.  
  
 L’exemple suivant génère l’erreur C3042 :  
  
```  
// C3042.cpp // compile with: /openmp /c #include <stdio.h> #include "omp.h" double d; int main() { #pragma omp parallel private(d) { #pragma omp single copyprivate(d) nowait   // C3042 { } } }  
```