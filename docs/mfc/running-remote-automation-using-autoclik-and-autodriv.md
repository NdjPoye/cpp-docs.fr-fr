---
title: "Exécution de l’Automation à distance à l’aide d’AUTOCLIK et AUTODRIV | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 791655047eaf07732e1e006e8cc3ea8e7dec4727
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>Exécution de l'automation à distance à l'aide d'AUTOCLIK et d'AUTODRIV
AUTOCLIK est une simple application exemple serveur Automation que vous pouvez utiliser comme base pour en savoir plus sur l’Automation à distance. AUTODRIV est une application cliente Automation simple qui utilise AUTOCLIK. Vous pouvez les utiliser pour illustrer l’Automation à distance.  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>Pour installer AUTOCLIK. EXE sur deux ordinateurs et de lecteur à l’aide d’Automation à distance  
  
1.  Installer le [AUTOCLIK](../visual-cpp-samples.md) exemple d’application sur votre ordinateur de développement.  
  
2.  Générez AUTOCLIK. EXE.  
  
3.  Exécutez AUTOCLIK. EXE dans autonome mode et arrêtez-le. Il sera inscrit en tant que serveur Automation.  
  
4.  Copiez AUTOCLIK. EXE sur un ordinateur distant, exécuter et arrêtez-le.  
  
5.  Exécutez AUTODRIV. Fichier EXE sur l’ordinateur local et vérifiez que son exécution démarre AUTOCLIK. EXE. Pour plus d’informations sur AUTODRIV. EXE, consultez [AUTOCLIK](../visual-cpp-samples.md).  
  
6.  Sur l’ordinateur distant, démarrez AUTMGR32. EXE (Gestionnaire d’Automation).  
  
7.  Sur l’ordinateur distant, démarrez RACMGR32. EXE (Gestionnaire de connexion d’Automation à distance).  
  
8.  Dans le Gestionnaire de connexions de Automation à distance, sélectionnez AutoClik.Document à partir de la **Classes OLE** liste.  
  
9. Choisir une stratégie de sécurité système à partir de la **accès Client** onglet pour accorder l’accès client à AutoClik.Document.  
  
10. Sur l’ordinateur local, démarrez RACMGR32. EXE et sélectionnez AutoClik.Document à partir de la **Classes OLE** liste.  
  
11. À partir de la **connexion au serveur** , choisir l’adresse réseau de l’ordinateur distant et le protocole réseau approprié.  
  
12. Avec toujours AutoClik.Document sélectionné dans le **Classes OLE** zone de liste, choisissez la **distant** commande à partir de la `Register` menu.  
  
13. Sur l’ordinateur local, exécutez AUTODRIV. EXE ou l’équivalent AUTOCLIK. Clé MAK Visual Basic projet si vous souhaitez avoir un Visual Basic, au lieu de MFC, une client.  
  
 Sur l’ordinateur distant, vous devez maintenant être en mesure de voir AUTOCLIK qui exécute des commandes lancées depuis le client local.  
  
## <a name="see-also"></a>Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)

