---
title: "Erreur du compilateur C3035 | Microsoft Docs"
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
  - "C3035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3035"
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive 'ordered' OpenMP doit être liée directement à une directive 'for' ou 'parallel for' avec la clause 'ordered'  
  
 Une clause ordered incorrecte a été rencontrée.  
  
 L’exemple suivant génère l’erreur C3035 :  
  
```  
// C3035.cpp // compile with: /openmp /link vcomps.lib int main() { int n = 0, x, i; #pragma omp parallel private(n) { #pragma omp ordered   // C3035 // Try the following line instead: // #pragma omp for ordered for (i = 0 ; i < 10 ; ++i) ; } }  
```