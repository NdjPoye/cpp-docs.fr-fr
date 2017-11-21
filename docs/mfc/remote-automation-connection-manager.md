---
title: "Gestionnaire de connexion d’Automation à distance | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation clients [MFC], configuring for Remote Automation
- registry [MFC], remote Automation
- Automation servers [MFC], configuring for Remote Automation
- Remote Automation Connection Manager [MFC]
- Remote Automation [MFC], configuring client and server machines
- RAC Manager tool [MFC]
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1a3085c92335aa6a2e0c5cd79cebb733688448a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="remote-automation-connection-manager"></a>Remote Automation Connection Manager (gestionnaire de connexion d'Automation à distance)
Pour configurer les ordinateurs client et serveur, vous devez modifier le Registre. Au lieu de cela manuellement, il est beaucoup plus facile à utiliser l’outil Gestionnaire de connexion d’Automation à distance (RAC). Cet outil, RACMGR32. EXE, avec RACREG32. DLL, doit être copié vers le répertoire de votre choix. En le plaçant dans le chemin d’accès, elle peut être exécutée à partir de la barre des tâches à l’aide de la série. Vous pouvez également créer un raccourci ou placer une référence à celle-ci dans le menu Démarrer.  
  
 RACMGR32 est écrit en Visual Basic et par conséquent a besoin de Visual Basic prennent en charge les DLL. Ces fichiers sont placés dans le même répertoire que RACMGR32. EXE sur le CD-ROM. Les versions de ces fichiers sont installés par le programme d’installation de Visual C++ Édition entreprise sont équivalentes ou plus récentes que celles fournies avec Visual Basic Enterprise Edition 5.0. L’installation de Visual C++ copie les nouvelles versions des fichiers Visual Basic dans votre répertoire système. Pour Windows 9 x, ce répertoire est en général C:\Windows\System. Pour Windows NT et Windows 2000, il est généralement C:\WINNT\system32. Le programme d’installation inscrit également ces fichiers avec le système d’exploitation. Vous pouvez les supprimer à partir de votre installation de Visual Basic.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaire d’Automation (MFC)](../mfc/automation-manager-mfc.md)   
 [Composants utilisateur d’Automation à distance](../mfc/remote-automation-user-components.md)   
 [Installation de l’Automation à distance](../mfc/remote-automation-installation.md)

