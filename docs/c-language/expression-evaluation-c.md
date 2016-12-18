---
title: "&#201;valuation d&#39;expression (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "évaluation d'expression"
  - "expressions (C++), évaluer"
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;valuation d&#39;expression (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les expressions impliquant une assignation, un incrément unaire, une décrémentation unaire, ou appelant une fonction peuvent avoir des conséquences sur leur évaluation \(effets secondaires\).  Lorsqu'un « point de séquence » est atteint, tout ce qui le précède, y compris tous les effets secondaires, est garanti avoir été évalué avant que l'évaluation commence sur tout ce qui suit le point de séquence.  
  
 Les « effets secondaires » sont des modifications déclenchées par l'évaluation d'une expression.  Les effets secondaires se produisent chaque fois que la valeur d'une variable est modifiée par une évaluation de l'expression.  Toutes les opérations d'assignation ont des effets secondaires.  Les appels de fonction peuvent également avoir des effets secondaires s'ils modifient la valeur d'un élément visible, par assignation directe ou indirecte via un pointeur.  
  
## Voir aussi  
 [Opérandes et expressions](../c-language/operands-and-expressions.md)