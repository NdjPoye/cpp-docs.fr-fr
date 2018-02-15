---
title: "Installation de l’Automation à distance | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-installation"></a>Installation de l'Automation à distance
Automation à distance a relativement peu de composants :  
  
-   Le proxy du client de l’Automation à distance, AUTPRX32. DLL.  
  
-   L’Automation à distance composant côté serveur, le Gestionnaire d’Automation, AUTMGR32. EXE.  
  
-   Le Gestionnaire RAC, RACMGR32. EXE, avec le fichier RACREG32. DLL.  
  
 Parmi ceux-ci, ce dernier est écrit en Visual Basic et par conséquent doit la durée d’exécution Visual Basic en charge. Ces et les autres fichiers de l’Automation à distance sont installés par le programme d’installation lorsque vous installez Visual C++ Édition entreprise.  
  
 Si vous copiez les composants d’Automation à distance sur un ordinateur sur la version de Visual C++, Édition entreprise n’est pas installée, assurez-vous que REGSRV32. EXE se trouve sur le chemin d’accès de l’ordinateur et inscrivez RACREG32. DLL à l’aide de la ligne de commande suivante :  
  
 REGSRVR32 RACREG32.DLL  
  
> [!NOTE]
>  Versions du Gestionnaire de certificat RAC avant Visual C++ 5.0 nécessitent GUAGE32. OCX et TABCTL32. OCX. Aucune de ces est requis pour la version de RAC Manager fourni avec Visual C++, Édition entreprise, version 5.0 ou ultérieure.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Le Gestionnaire d’Automation](../mfc/automation-manager-mfc.md)  
  
 [Le Gestionnaire de connexion d’Automation à distance](../mfc/remote-automation-connection-manager.md)  
  
 [Composants utilisateur d’Automation à distance](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)

