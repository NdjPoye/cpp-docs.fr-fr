---
title: "Erreur du compilateur C3058 | Microsoft Docs"
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
  - "C3058"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3058"
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3058
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : symbole non déclaré en tant que 'threadprivate' avant d’être utilisé dans la clause 'copyin'  
  
 Un symbole doit d’abord être déclaré en tant que [threadprivate](../../parallel/openmp/reference/threadprivate.md) avant de pouvoir être utilisé dans une clause [copyin](../../parallel/openmp/reference/copyin.md).  
  
 L’exemple suivant génère l’erreur C3058 :  
  
```  
// C3058.cpp // compile with: /openmp int x, y, z; #pragma omp threadprivate(x, z) void test() { #pragma omp parallel copyin(x, y)   // C3058 { } }  
```  
  
 Résolution possible :  
  
```  
// C3058b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { } }  
```