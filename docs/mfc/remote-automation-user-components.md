---
title: "Composants utilisateur d’Automation à distance | Documents Microsoft"
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
- DLLs [MFC], Automation
- Remote Automation [MFC], user components
ms.assetid: 601591cc-a442-440a-988e-baf3284b0d46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f82fe529586579109434da447e26b15dcb9503a
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-user-components"></a>Composants utilisateur d'Automation à distance
Vous devez vous assurer que chaque machine cliente contient votre programme client et la prise en charge de toutes les DLL requises. Vous devez également vous assurer que l’application serveur et les DLL requises de la prise en charge sont présents sur l’ordinateur serveur. Enfin, vous devez vous assurer que votre programme serveur est inscrit sur chaque ordinateur client avant de pouvoir exécuter RAC Manager pour configurer la connexion. Si le programme s’inscrit automatiquement (comme la plupart seront), vous devez uniquement exécuter le programme de serveur sur l’ordinateur client pour l’inscrire. À défaut, vous devrez peut-être exécuter un fichier d’inscription que vous fournissez, ou bien modifier manuellement le Registre.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestionnaire d’Automation (MFC)](../mfc/automation-manager-mfc.md)   
 [Gestionnaire de connexion d’Automation à distance](../mfc/remote-automation-connection-manager.md)   
 [Installation de l’Automation à distance](../mfc/remote-automation-installation.md)

