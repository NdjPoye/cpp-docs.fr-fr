---
title: "Erreur du compilateur C3037 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3037"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3037"
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3037
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : la variable de la clause 'reduction' doit être partagée dans un contexte englobant  
  
 Une variable spécifiée dans une clause [reduction](../../parallel/openmp/reference/reduction.md) ne peut pas être privée pour chaque thread dans le contexte.  
  
 L’exemple suivant génère l’erreur C3037 :  
  
```  
// C3037.cpp // compile with: /openmp /c int g_i; int main() { int i; #pragma omp parallel private(g_i) // try the following line instead // #pragma omp parallel { #pragma omp for reduction(+:g_i)   // C3037 for (i = 0 ; i < 10 ; ++i) { g_i += i; } } }  
```