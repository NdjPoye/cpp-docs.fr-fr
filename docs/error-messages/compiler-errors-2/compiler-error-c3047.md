---
title: "Erreur du compilateur C3047 | Microsoft Docs"
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
  - "C3047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3047"
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le bloc structuré d'une région 'sections' OpenMP doit être précédé de '\#pragma omp section'  
  
 Tout code contenu dans un bloc de code introduit par une directive [sections](../../parallel/openmp/reference/sections-openmp.md) doit se trouver dans un bloc de code introduit par une directive `section`.  
  
 L’exemple suivant génère l’erreur C3047 :  
  
```  
// C3047.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections { #pragma omp section { ++n3; } ++n2;   // C3047 not enclosed in #pragma omp section } } }  
```