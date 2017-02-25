---
title: "R6009 d’erreur d’ex&#233;cution C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6009"
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur d&#39;ex&#233;cution C R6009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

espace insuffisant pour l'environnement  
  
 La mémoire était suffisante pour charger le programme mais insuffisante pour créer le tableau **envp**.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Augmentez la quantité de mémoire dont dispose le programme.  
  
2.  Réduisez le nombre et la taille des arguments sur la ligne de commande.  
  
3.  Réduisez la taille de l'environnement en supprimant les variables superflues.