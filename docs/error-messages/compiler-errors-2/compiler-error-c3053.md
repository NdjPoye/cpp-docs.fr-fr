---
title: "Erreur du compilateur C3053 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3053"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3053"
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3053
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : 'threadprivate' n’est valide que pour les éléments de données global ou static  
  
 Les symboles passés à [threadprivate](../../parallel/openmp/reference/threadprivate.md) doivent être de type global ou static.  
  
 L’exemple suivant génère l’erreur C3053 :  
  
```  
// C3053.cpp // compile with: /openmp void Test() { int x, y; #pragma omp threadprivate(x, y)   // C3053 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 Résolution possible :  
  
```  
// C3053b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void Test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```