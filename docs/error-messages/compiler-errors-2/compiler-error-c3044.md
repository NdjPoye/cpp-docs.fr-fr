---
title: "Erreur du compilateur C3044 | Microsoft Docs"
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
  - "C3044"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3044"
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3044
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'section' : uniquement autorisé lors d’une imbrication directe sous une directive 'sections' OpenMP  
  
 Le compilateur a rencontré une directive `section` qui n’a pas été utilisée correctement. Pour plus d’informations, consultez [sections](../../parallel/openmp/reference/sections-openmp.md).  
  
 L’exemple suivant génère l’erreur C3044 :  
  
```  
// C3044.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { ++n2; } #pragma omp section   // C3044 { ++n3; } } #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section   // OK { ++n3; } } } }  
```