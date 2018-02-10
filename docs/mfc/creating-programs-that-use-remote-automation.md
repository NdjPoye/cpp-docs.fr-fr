---
title: "Création de programmes qui utilisent l’Automation à distance | Documents Microsoft"
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
- Remote Automation, creating programs
ms.assetid: 8eb31320-1037-4029-b1f3-fdc9406dbaf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86a9b9f4dccaaa3a97366dffb11955d3b148aff5
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="creating-programs-that-use-remote-automation"></a>Création de programmes qui utilisent l'automation à distance
N’importe quel objet automation et n’importe quel contrôleur automation, est en mesure d’utiliser l’Automation à distance sans modification sur le code source, sans nécessiter de recompilation et sans reconstruction. Une fois que vous avez un programme d’installation qui fonctionne localement (c'est-à-dire sur le même ordinateur), vous devez parcourir uniquement quelques étapes à exécuter à distance.  
  
#### <a name="to-execute-the-remote-automation-object"></a>Pour exécuter l’objet Automation à distance  
  
1.  Inscrire l’application sur les ordinateurs client.  
  
2.  Configurer l’accès client pour utiliser le serveur distant.  
  
3.  Installez et inscrivez l’application sur le serveur ou des ordinateurs.  
  
4.  Configurer le serveur pour autoriser l’activation à distance.  
  
5.  Installez le Gestionnaire d’Automation sur les machines serveur.  
  
6.  Exécutez le Gestionnaire d’Automation sur les serveurs.  
  
7.  Exécutez l’application sur les clients.  
  
 Étape 1 s’effectue plus facilement en chargeant et en exécutant l’application serveur sur l’ordinateur client, comme la plupart des serveurs s’inscrivent. Si vous avez testé le programme d’installation localement au préalable, cette étape est déjà terminée. Si l’application serveur n’est pas inscription automatique, vous pouvez souhaiter qu’elle le fasse. Dans le cas contraire, vous devez fournir un fichier d’inscription que l’utilisateur local peut exécuter pour effectuer cette étape. Si vous n’effectuez aucune de ces éléments, un administrateur ou vous-même devez modifier le Registre manuellement, une procédure qui n’est pas recommandée pour toutes les utilisateurs plus expérimentés.  
  
 Étape 2 implique l’utilisation du Gestionnaire de connexion d’Automation à distance (RAC). Exécutez le Gestionnaire RAC et assurez-vous que l’onglet Connexion de serveur est plus élevé. Ensuite, recherchez l’entrée de l’objet serveur dans le **Classes OLE** volet et cliquez dessus. Ensuite, passez à la **adresse réseau** liste déroulante zone, entrez le nom de l’ordinateur serveur sur lequel le fichier exécutable distant est exécuté. Par exemple, vous pouvez entrer \\\MyServer ici. Sélectionnez ensuite le protocole réseau approprié dans la liste fournie. Vous devrez peut-être vérifier avec votre administrateur réseau pour déterminer quel protocole est recommandé. Dans de nombreux cas, il s’agit de TCP/IP. Enfin, vous voudrez choisir un niveau d’authentification. Dans la plupart des cas, il s’agit de gauche à (None) ou par défaut. Maintenant que vous cliquez sur le serveur dans le **Classes OLE** volet. Cela génère un menu contextuel à partir de laquelle vous pouvez sélectionner opération locale ou distante. Sélectionnez à distance.  
  
 Étape 3 implique l’installation et l’inscription de l’application serveur sur le serveur sélectionné ou des ordinateurs correctement. Là encore, si l’application est l’inscription automatique, une fois son exécution inscrira également.  
  
 Étape 4 implique la configuration du serveur pour permettre l’exécution à distance. Exécutez le Gestionnaire RAC sur l’ordinateur serveur et vérifiez que le **accès Client** onglet a le focus. Choisissez le modèle d’activation que vous souhaitez (généralement **autoriser à distance crée par clé**. Si vous choisissez cette option, vous devez également cliquer sur le **autoriser l’Activation à distance** case à cocher pour définir la valeur de l’entrée de Registre à 'Y'). Si vous choisissez l’option Autoriser à distance crée (ACL), vous avez également la possibilité pour modifier la liste ACL en envoyant la **modifier la liste ACL** bouton.  
  
 Pour permettre l’Automation à distance fonctionne, vous devez vous assurer que le Gestionnaire d’Automation est installé et en cours d’exécution sur le serveur ou des ordinateurs. S’il n’est pas installé, copiez AUTMGR32. EXE pour le répertoire système Windows. Pour plus d’informations sur la marche à suivre, consultez [Installation de l’Automation à distance](../mfc/remote-automation-installation.md). Pour démarrer l’Automation à distance, exécutez le Gestionnaire d’Automation. Il affiche une petite fenêtre d’état dans lequel un nombre de messages s’affichera. Une fois qu’il a démarré, il réduira lui-même. Si vous souhaitez continuer de voir les informations d’état, vous pouvez cliquer sur le **Gestionnaire d’Automation** onglet dans la barre des tâches pour restaurer la fenêtre.  
  
 L’étape finale consiste à exécuter de l’application cliente sur l’ordinateur client. Si vous avez suivi les étapes ci-dessus, il doit se connecter à l’objet serveur et l’exécuter comme en local, mais il est plus lente.  
  
 Notez que le Gestionnaire de connexion vous permet également de basculer entre l’Automation à distance et de distributed COM (DCOM sur ces plateformes qui prennent en charge DCOM) d’un simple clic d’un bouton radio. Si vous choisissez DCOM, vous pouvez définir plusieurs options de configuration. Consultez la documentation de DCOM pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)   
 [Exécution d’Automation à distance à l’aide d’AUTOCLIK et d’AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)

