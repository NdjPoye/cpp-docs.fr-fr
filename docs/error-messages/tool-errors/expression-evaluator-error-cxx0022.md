---
title: "&#201;valuateur d&#39;expression, erreur CXX0022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0022"
  - "CXX0022"
ms.assetid: f6b299ac-a4ee-492c-bd9f-6fff005bc537
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;valuateur d&#39;expression, erreur CXX0022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

appel de fonction avant \_main  
  
 L'évaluateur d'expression C ne peut pas évaluer une fonction avant que le débogueur n'entre dans **\_main** de la fonction.  Le programme n'est pas correctement initialisé tant que **\_main** n'est pas appelé.  
  
 Erreur identique à CAN0022.