---
title: "Erreur BSCMAKE BK1509 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1509"
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur BSCMAKE BK1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace du tas insuffisant  
  
 BSCMAKE manque de mémoire, y compris de mémoire virtuelle.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Libérez de l'espace disque  
  
2.  Augmentez la taille du fichier d'échange.  
  
3.  Augmentez la taille du fichier d'échange de Windows.  
  
4.  Réduisez la mémoire nécessaire à BSCMAKE en utilisant l'option \/Ei ou \/Es pour éliminer des fichiers d'entrée ou l'option \/Em pour éliminer les corps de certaines macros.