---
title: Déployer une Application Visual C++ à l’aide d’un projet d’installation | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 454507a3a3f33b43af0e50c25dab6703aa75a56b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Procédure pas à pas : déploiement d'une application Visual C++ à l'aide d'un projet d'installation
Décrit comment utiliser un projet d’installation pour déployer une application Visual C++.  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :  
  
-   Un ordinateur avec [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] installé.  
  
-   Un ordinateur supplémentaire qui n’a pas les bibliothèques Visual C++.  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Pour déployer une application à l’aide d’un projet d’installation  
  
1.  Utilisez le **MFC ApplicationWizard** pour créer une nouvelle solution Visual Studio. Pour rechercher l’Assistant, à partir du **nouveau projet** boîte de dialogue, développez le **Visual C++** nœud, sélectionnez **MFC**, sélectionnez **Application MFC**, entrez un nom du projet, puis cliquez sur **OK**.  
  
2.  Passez à la configuration de solution active **version**. À partir de la **générer** menu, sélectionnez **Gestionnaire de Configuration**. À partir de la **Configuration Manager** boîte de dialogue, sélectionnez **version** à partir de la **configuration de solution Active** zone de liste déroulante.  
  
3.  Appuyez sur F7 pour générer l’application. Ou, dans le **générer** menu, cliquez sur **générer la Solution**. Ainsi, le projet d’installation utiliser la sortie de ce projet d’application MFC.  
  
4.  Si vous n’avez pas déjà fait, téléchargez InstallShield Limited Edition (ISLE), qui est gratuit pour les développeurs Visual Studio et remplace la fonctionnalité des modèles de projet dans Visual Studio pour le déploiement et le programme d’installation. Lorsque vous êtes connecté à Internet, ouvrez le **nouveau projet** boîte de dialogue en choisissant **fichier**, **nouveau**, **projet** dans le menu de la barre, ou par clic droit sur votre solution dans **l’Explorateur de solutions** et en choisissant **ajouter**, **nouveau projet**. Développez le **autres Types de projets** nœud, choisissez **Activer InstallShield Limited Edition** dans le **le programme d’installation et de déploiement** nœud, puis suivez les instructions qui s’affichent. Une fois que vous avez téléchargé, installé et activé InstallShield Limited Edition, fermez Visual Studio et ouvrez à nouveau.  
  
5.  Ouvrez le **nouveau projet** boîte de dialogue, développez le **autres Types de projets** nœud et choisissez **projet InstallShield Limited Edition** dans le  **InstallShield Limited Edition** nœud.  
  
6.  Suivez les instructions fournies dans le **mise en route** nœud du projet d’installation créé par le modèle de InstallShield Limited Edition pour ajouter une référence de sortie à votre projet MFC de Visual Studio.  
  
7.  Générez le projet d’installation pour créer le fichier de programme d’installation (setup.exe). Pour ce faire, cliquez avec le bouton droit sur le nœud du projet dans le programme d’installation **l’Explorateur de solutions** et sélectionnez **Build**.  
  
     InstallShield Limited Edition crée le fichier d’installation dans l’arborescence du projet d’installation (par défaut, il peut se trouver dans le sous-dossier Express\SingleImage\DiskImages\DISK1 du projet d’installation).  
  
8.  Exécutez le programme d’installation sur un deuxième ordinateur qui ne dispose pas des bibliothèques Visual C++.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)