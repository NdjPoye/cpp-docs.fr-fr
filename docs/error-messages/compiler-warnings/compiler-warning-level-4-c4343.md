---
title: "Avertissement du compilateur (niveau&#160;4) C4343 | Microsoft Docs"
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
  - "C4343"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4343"
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4343
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma optimize\("g",off\) se substitue à l’option \/Og  
  
 Cet avertissement, qui s’applique uniquement aux compilateurs de processeurs Itanium \(IPF\), signale qu’un pragma [optimize](../../preprocessor/optimize.md) a remplacé une option [\/Og](../../build/reference/og-global-optimizations.md) du compilateur.  
  
 L’exemple suivant génère l’avertissement C4343 :  
  
```  
// C4343.cpp // compile with: /Og /W4 /LD // processor: IPF #pragma optimize ("g", off)   // C4343  
```