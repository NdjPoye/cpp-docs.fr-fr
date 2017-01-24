---
title: "Erreur BSCMAKE BK1506 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1506"
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur BSCMAKE BK1506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir le fichier 'nom\_fichier' \[: raison\]  
  
 BSCMAKE ne peut pas ouvrir le fichier.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le fichier est verrouillé par un autre processus.  Si `reason` indique **Autorisation refusée**, il se peut que le navigateur soit en train d'utiliser le fichier.  Fermez la fenêtre de consultation et recommencez la génération.  
  
2.  Un disque plein.  
  
3.  Une erreur matérielle.  
  
4.  Le fichier de sortie spécifié a le même nom qu'un sous\-répertoire existant.