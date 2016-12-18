---
title: "ML Nonfatal Error A2066 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2066"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2066"
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Nonfatal Error A2066
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**mode incompatible d'UC et la taille de segment**  
  
 Une tentative a été faite ouvrir un segment avec un attribut d' **USE16**, d' **USE32**, ou d' **APPARTEMENT** qui n'était pas compatible avec le processeur spécifié, ou de passer à un processeur 16 bits en un segment 32 bits.  
  
 Les attributs d' **USE32** et d' **APPARTEMENT** doivent être précédés par le .386 ou la directive supérieure du processeur.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)