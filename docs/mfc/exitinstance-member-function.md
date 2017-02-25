---
title: "ExitInstance, fonction membre | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp::ExitInstance"
  - "CWinApp.ExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp (classe), ExitInstance"
  - "ExitInstance (méthode)"
  - "programmes (C++), terminer"
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ExitInstance, fonction membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonction membre [ExitInstance](../Topic/CWinApp::ExitInstance.md) de la classe [CWinApp](../mfc/reference/cwinapp-class.md) est appelée chaque fois qu'une copie de l'application se termine, généralement suite à l'utilisateur de la sortie l'application.  
  
 Remplacez `ExitInstance` si vous avez besoin de nettoyage traitement spécial, tel que libérer des ressources \(GDI\) de Graphics Device Interface ou libérer de la mémoire utilisée pendant l'exécution du programme.  Le nettoyage des éléments standard tels que des documents et des vues, toutefois, par l'infrastructure, avec d'autres fonctions substituables pour effectuer des informations spécial de nettoyage à ces objets.  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)