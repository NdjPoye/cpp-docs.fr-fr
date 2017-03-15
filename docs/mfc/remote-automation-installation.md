---
title: "Installation de l&#39;Automation &#224; distance | Microsoft Docs"
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
helpviewer_keywords: 
  - "installer l'Automation à distance"
  - "Automation à distance, installation"
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Installation de l&#39;Automation &#224; distance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'automatisation distante a relativement peu de composants.  
  
-   Le proxy client d'automatisation à distance, AUTPRX32.DLL.  
  
-   Le composant côté serveur d'automatisation à distance, Gestionnaire d'automation, AUTMGR32.EXE.  
  
-   Le gestionnaire RAC, RACMGR32.EXE, avec sa correspondance RACREG32.DLL.  
  
 Sur ceux\-ci, le gestionnaire RAC est écrit dans Visual Basic et requiert donc une prise en charge de la librairie de Visual Basic run\-time.  Celles\-ci et les autres fichiers d'automatisation distante sont installés par le programme d'installation si vous installez Visual C\+\+ Enterprise Edition.  
  
 Si vous copiez des composants d'automatisation à distance sur un ordinateur sur lequel la version de Visual C\+\+ Enterprise Edition est installée, vérifiez que REGSRV32.EXE est dans le chemin d'accès de l'ordinateur, et le registre RACREG32.DLL à la ligne de commande suivante :  
  
 REGSRVR32 RACREG32.DLL  
  
> [!NOTE]
>  Les versions du gestionnaire RAC avant Visual C\+\+ 5.0 demandaient GUAGE32.OCX et TABCTL32.OCX.  Aucune de ces dernières n'est requise pour la version du gestionnaire RAC fournie avec Visual C\+\+ Enterprise Edition, la version 5,0 ou celle ultérieure.  
  
## Dans cette section  
 [Le gestionnaire d'Automation](../mfc/automation-manager-mfc.md)  
  
 [Le gestionnaire de connexion automatique à distance.](../mfc/remote-automation-connection-manager.md)  
  
 [Composants utilisateur d'automation à distance](../mfc/remote-automation-user-components.md)  
  
## Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)