---
title: "Erreur du compilateur C3045 | Microsoft Docs"
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
  - "C3045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3045"
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instruction composée attendue à la suite de la directive 'sections' OpenMP. Accolade '{' manquante  
  
 Un bloc de code délimité par des accolades doit suivre une directive [sections](../../parallel/openmp/reference/sections-openmp.md).  
  
 L’exemple suivant génère l’erreur C3045 :  
  
```  
// C3045.cpp // compile with: /openmp /c #include "omp.h" int main() { int n2 = 2, n3 = 3; #pragma omp parallel { ++n2; #pragma omp sections ++n2;   // C3045 #pragma omp sections   // OK { ++n3; } } }  
```