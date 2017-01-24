---
title: "Erreur du compilateur C3036 | Microsoft Docs"
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
  - "C3036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3036"
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : jeton d’opérateur non valide dans la clause 'reduction' OpenMP  
  
 Une clause [reduction](../../parallel/openmp/reference/reduction.md) n’a pas été spécifiée correctement.  
  
 L’exemple suivant génère l’erreur C3036 :  
  
```  
// C3036.cpp // compile with: /openmp static float a[1000], b[1000], c[1000]; void test1(int first, int last) { static float dp = 0.0f; #pragma omp for nowait reduction(.:dp)   // C3036 // try the following line instead // #pragma omp for nowait reduction(+: dp) for (int i = first ; i <= last ; ++i) dp += a[i] * b[i]; }  
```