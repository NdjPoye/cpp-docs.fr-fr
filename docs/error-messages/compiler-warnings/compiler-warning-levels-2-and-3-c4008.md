---
title: "Avertissement du compilateur (niveaux&#160;2 et&#160;3) C4008 | Microsoft Docs"
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
  - "C4008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4008"
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveaux&#160;2 et&#160;3) C4008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'attribute' attribut ignoré  
  
 Le compilateur a ignoré l’attribut `__fastcall`, **static** ou **inline** pour une fonction \(avertissement de niveau 3\) ou des données \(avertissement de niveau 2\).  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Attribut `__fastcall` avec des données.  
  
2.  Attribut **static** ou **inline** avec la fonction **main**.