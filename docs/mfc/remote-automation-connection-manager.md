---
title: "Remote Automation Connection Manager (gestionnaire de connexion d&#39;Automation &#224; distance) | Microsoft Docs"
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
helpviewer_keywords: 
  - "clients Automation, configurer pour l'Automation à distance"
  - "Automation (serveurs), configurer pour l'Automation à distance"
  - "RAC Manager (outil)"
  - "Registre, Automation à distance"
  - "Remote Automation Connection Manager (gestionnaire de connexion d'Automation à distance)"
  - "Automation à distance, configurer les ordinateurs serveurs et clients"
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Remote Automation Connection Manager (gestionnaire de connexion d&#39;Automation &#224; distance)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour configurer les deux ordinateurs clients et serveurs, vous devez apporter vos modifications dans le Registre.  Plutôt que cette opération à la main, il est beaucoup plus facile d'utiliser l'outil gestionnaire de \(RAC\) de connexion d'automatisation à distance.  Cet outil, RACMGR32.EXE, avec RACREG32.DLL, doit être copié dans n'importe quel dossier de votre choix.  En mettant en PATH, il peut être exécutée à partir de la barre des tâches à exécuter.  Ou bien, vous pouvez créer un raccourci à utiliser ou placer une référence à celui\-ci dans le menu Démarrer.  
  
 RACMGR32 est écrit dans Visual Basic et requiert donc des DLL en Visual Basic.  Ces fichiers se trouvent dans le même répertoire que RACMGR32.EXE sur le CD\-ROM.  Les versions de ces fichiers qui sont installés par le programme d'installation de Visual C\+\+ Enterprise Edition sont équivalentes ou plus récentes que celles qui ont fourni avec Visual Basic Enterprise Edition 5,0.  L'installation de Visual C\+\+ copie les nouvelles versions des fichiers Visual Basic à votre répertoire système.  Pour Windows. 9x, ce répertoire est généralement C:\\Windows\\System.  Pour Windows NT et Windows 2000, il s'agit généralement C:\\WINNT\\system32.  Le programme d'installation enregistre également ces fichiers avec le système d'exploitation.  Vous pouvez les supprimer de l'installation de Visual Basic.  
  
## Voir aussi  
 [Gestionnaire d'Automation \(MFC\)](../mfc/automation-manager-mfc.md)   
 [Composants utilisateur d'Automation à distance](../mfc/remote-automation-user-components.md)   
 [Installation de l'Automation à distance](../mfc/remote-automation-installation.md)