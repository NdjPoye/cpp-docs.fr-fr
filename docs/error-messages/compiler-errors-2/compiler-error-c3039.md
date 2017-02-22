---
title: "Erreur du compilateur C3039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3039"
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : la variable d’index de l’instruction 'for' OpenMP ne peut pas être une variable de réduction  
  
 Une variable d’index est implicitement privée. Elle ne peut donc pas être utilisée dans une clause [reduction](../../parallel/openmp/reference/reduction.md) dans la directive [parallel](../../parallel/openmp/reference/parallel.md) englobante.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3039 :  
  
```  
// C3039.cpp // compile with: /openmp /c int g_i; int main() { int i; #pragma omp parallel reduction(+: i) { #pragma omp for for (i = 0; i < 10; ++i)   // C3039 g_i += i; } }  
```