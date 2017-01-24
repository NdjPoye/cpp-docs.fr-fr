---
title: "Prise en charge de la virgule flottante pour le code plus ancien (Visual C++) | Microsoft Docs"
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
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Prise en charge de la virgule flottante pour le code plus ancien (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les registres de pile à virgule flottante et MMX \(MM0\-MM7\/ST0\-ST7\) sont conservés entre les commutateurs de contexte.  Il n'existe aucune convention d'appel explicite pour ces registres.  Leur utilisation est strictement interdite dans le code en mode noyau.  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)