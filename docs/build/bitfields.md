---
title: "Champs de bits | Microsoft Docs"
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
  - "champs de bits"
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Champs de bits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les champs de bits de structures sont limités à 64 bits et peuvent être de type signed int, unsigned int, int64 ou unsigned int64.  Les champs de bits qui dépassent la limite de type ignorent les bits pour aligner le champ de bits à l'alignement du type suivant.  Par exemple, les champs de bits entiers ne peuvent pas dépasser une limite de 32 bits.  
  
## Voir aussi  
 [Types et stockage](../build/types-and-storage.md)