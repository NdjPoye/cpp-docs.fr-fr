---
title: "Erreur du compilateur C3046 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3046"
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bloc structuré manquant dans une région '\#pragma omp sections' OpenMP  
  
 Une directive [sections](../../parallel/openmp/reference/sections-openmp.md) comprend un bloc de code vide.  
  
 L’exemple suivant génère l’erreur C3046 :  
  
```  
// C3046.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { /* ++n2; #pragma omp section { ++n3; } */ }   // C3046 uncomment code to resolve this C3046 } }  
```