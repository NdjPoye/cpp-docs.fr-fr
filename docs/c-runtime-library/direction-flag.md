---
title: "Balise de direction | Microsoft Docs"
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
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "balise de direction"
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Balise de direction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'indicateur de direction est un ensemble de balises UC sur les processeurs Intel 80x86.  Elle s'applique à toutes les instructions assemblys qui utilisent le préfixe de REPRÉSENTANT \(répétition\), tel que MOVS, MOVSD, MOVSW, entre autres.  Les adresses fournies à l'instruction applicables sont augmenté si l'indicateur de direction est désactivée.  
  
 Les routines de runtime C supposent que l'indicateur de direction est désactivée.  Si vous utilisez d'autres fonctions avec les fonctions runtime C, vous devez vous assurer que les autres fonctions permettent l'indicateur de direction seule ou la restauration à son état initial.  En prévoyant que l'indicateur de direction est claire sur l'entrée de code à l'exécution plus rapide et plus efficace.  
  
 Les fonctions de la bibliothèque runtime C, telles que la suivante par manipulation et les routines de mémoire tampon\-\), attendez\-vous à ce que l'indicateur de direction à effacer.  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)