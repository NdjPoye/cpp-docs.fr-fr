---
title: "Erreur du compilateur C3021 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3021"
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : argument vide dans la directive OpenMP 'directive'  
  
 Un argument est requis pour une directive OpenMP.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3021 :  
  
```  
// C3021.cpp // compile with: /openmp #include <stdio.h> #include "omp.h" int g = 0; int main() { int x, y, i; #pragma omp parallel for schedule(static,)   // C3021 for (i = 0; i < 10; ++i) ; #pragma omp parallel for schedule()   // C3021 for (i = 0; i < 10; ++i) printf_s("Hello world, thread %d, iteration %d\n", omp_get_thread_num(), i); #pragma omp parallel reduction()   // C3021 ; #pragma omp parallel reduction(+ :)   // C3021 ; // // The following shows correct syntax examples. // #pragma omp parallel reduction(+ : x, y) ; #pragma omp parallel reduction(* : x, y) ; #pragma omp parallel reduction(- : x, y) ; #pragma omp parallel reduction(& : x, y) ; #pragma omp parallel reduction(^ : x, y) ; #pragma omp parallel reduction(| : x, y) ; #pragma omp parallel reduction(&& : x, y) ; #pragma omp parallel reduction(|| : x, y) ; }  
```