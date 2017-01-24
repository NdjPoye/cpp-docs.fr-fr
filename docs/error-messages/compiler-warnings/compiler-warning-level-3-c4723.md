---
title: "Avertissement du compilateur (niveau 3) C4723 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

risque de division par 0  
  
 Le second opérande dans une division prenait la valeur zéro au moment de la compilation, donnant ainsi des résultats indéterminés.  
  
 Cet avertissement est généré seulement lorsque vous utilisez [\/Og](../../build/reference/og-global-optimizations.md) ou une option d'optimisation qui fait appel à \/Og.  
  
 Le compilateur a peut\-être généré l'opérande nul.