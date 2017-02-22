---
title: "alloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b209335-e3a0-4934-93f0-3b5925d22918
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# alloca
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\_alloca](../c-runtime-library/reference/alloca.md) est doit être aligné sur 16 octets et utiliser un pointeur de frame.  
  
 La pile allouée doit inclure de l'espace en dessous d'elle pour les paramètres des fonctions appelées par la suite, comme expliqué dans la rubrique [Allocation de piles](../build/stack-allocation.md).  
  
## Voir aussi  
 [Utilisation de la pile](../build/stack-usage.md)