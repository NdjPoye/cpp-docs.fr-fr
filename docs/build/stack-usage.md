---
title: "Utilisation de la pile | Microsoft Docs"
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
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Utilisation de la pile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Toute la mémoire au\-delà de l'adresse actuelle de RSP est considérée volatile : le système d'exploitation, ou un débogueur, peut remplacer cette mémoire pendant une session de débogage par l'utilisateur ou un gestionnaire d'interruption.  Par conséquent, RSP doit toujours être défini avant de tenter de lire ou d'écrire des valeurs dans un frame de pile.  
  
 Cette section décrit l'allocation d'espace de pile pour des variables locales et l'**alloca** intrinsèque.  
  
-   [Allocation de piles](../build/stack-allocation.md)  
  
-   [Construction dynamique d'une zone pour la pile de paramètres](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Types de fonctions](../build/function-types.md)  
  
-   [Alignement avec malloc](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)