---
title: "D&#233;passement n&#233;gatif de valeurs &#224; virgule flottante | Microsoft Docs"
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
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;passement n&#233;gatif de valeurs &#224; virgule flottante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.5.1** Indique si les fonctions mathématiques définissent l'expression d'entier `errno` sur la valeur de la macro `ERANGE` sur les erreurs de plage de dépassement de capacité négatif  
  
 Un dépassement de capacité négatif à virgule flottante ne définit pas l'expression `errno` sur `ERANGE`.  Lorsqu'une valeur s'approche de zéro et effectue finalement un dépassement de capacité négatif, la valeur est définie sur zéro.  
  
## Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)