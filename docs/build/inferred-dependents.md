---
title: "D&#233;pendants inf&#233;r&#233;s | Microsoft Docs"
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
helpviewer_keywords: 
  - "dépendants, déduites"
  - "dépendants inférés dans NMAKE"
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;pendants inf&#233;r&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un dépendant déduit est dérivé d'une règle d'inférence et est évalué avant les dépendants explicites.  Si un dépendant déduit est obsolète par rapport à sa cible, NMAKE appelle le bloc de commandes de la dépendance.  Si un dépendant déduit n'existe pas ou est obsolète par rapport à ses propres dépendants, NMAKE met à jour le dépendant déduit en premier.  Pour plus d'informations sur les dépendants déduits, consultez la rubrique [Règles d'inférence](../build/inference-rules.md).  
  
## Voir aussi  
 [Dépendants](../build/dependents.md)