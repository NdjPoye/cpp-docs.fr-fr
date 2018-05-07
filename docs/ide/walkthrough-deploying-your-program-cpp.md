---
title: 'Procédure pas à pas : Déploiement de votre programme (C++) | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1753c63673b9dd083e2b690788801bd467938c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-your-program-c"></a>Procédure pas à pas : déploiement de votre programme (C++)
Maintenant que vous avez créé votre application en effectuant le plus haut connexes procédures pas à pas, qui sont répertoriées dans [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md), la dernière étape consiste à créer un programme d’installation afin que les autres utilisateurs installer le programme sur leurs ordinateurs. Pour cela, vous allez ajouter un nouveau projet à votre solution existante. La sortie de ce nouveau projet est un fichier setup.exe qui installe votre application sur un autre ordinateur.  
  
 Cette procédure pas à pas indique comment utiliser Windows Installer pour déployer votre application. Vous pouvez également utiliser ClickOnce pour déployer une application. Pour plus d’informations, consultez [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md). Pour plus d’informations sur le déploiement en général, consultez [déploiement d’Applications, Services et composants](/visualstudio/deployment/deploying-applications-services-and-components).  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Cette procédure pas à pas part du principe que vous comprenez les notions de base du langage C++.  
  
-   Il suppose également que vous avez effectué les procédures plus haut connexes qui sont répertoriés dans [à l’aide de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
-   Cette procédure pas à pas ne peut pas être effectuée dans les éditions Express de Visual Studio.  
  
-   Si ce n'est déjà fait, téléchargez InstallShield Limited Edition (ISLE), comme indiqué dans la procédure plus loin dans cet article. ISLE est une version gratuite d'InstallShield pour les développeurs Visual Studio qui remplace les fonctionnalités des modèles de projet d'installation et de déploiement présents dans les éditions antérieures de Visual Studio.  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>Pour installer le modèle de projet d'installation et de déploiement ISLE  
  
1.  Lorsque vous êtes connecté à Internet, dans la barre de menus, choisissez **fichier**, **nouveau**, **projet** pour ouvrir le **nouveau projet** boîte de dialogue.  
  
2.  Dans le volet gauche de la boîte de dialogue, développez le **installé**, **modèles**, et **autres Types de projets** nœuds, puis sélectionnez **le programme d’installation et de déploiement**. Dans le volet central, sélectionnez **Activer InstallShield Limited Edition** , puis choisissez le **OK** bouton.  
  
3.  Suivez les instructions pour installer InstallShield Limited Edition pour Visual Studio (ISLE).  
  
4.  Après avoir téléchargé, installé et activé ISLE, fermez Visual Studio et rouvrez-le.  
  
5.  Dans la barre de menus, choisissez **fichier**, **projets et Solutions récents**, puis choisissez le **jeu** solution pour la rouvrir.  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>Pour créer un projet d'installation et installer votre programme  
  
1.  Modifiez la configuration de solution active en Mise en production. Dans la barre de menus, choisissez **Générer**, puis **Gestionnaire de configurations**. Dans le **Configuration Manager** boîte de dialogue le **configuration de solution Active** la liste déroulante, sélectionnez **version**. Choisissez le **fermer** bouton pour enregistrer la configuration.  
  
2.  Dans la barre de menus, choisissez **fichier**, **nouveau**, **projet** pour ouvrir le **nouveau projet** boîte de dialogue.  
  
3.  Dans le volet gauche de la boîte de dialogue, développez le **installé**, **modèles**, et **autres Types de projets** nœuds, puis sélectionnez **le programme d’installation et de déploiement**. Dans le volet central, sélectionnez **projet InstallShield Limited Edition**.  
  
4.  Entrez un nom pour le projet d’installation dans le **nom** boîte. Par exemple, entrez **Game Installer**. Dans le **Solution** la liste déroulante, sélectionnez **ajouter à la solution**. Choisissez le **OK** bouton permettant de créer le projet d’installation. A **Assistant projet (Game Installer)** onglet s’ouvre dans la fenêtre de l’éditeur.  
  
5.  Au bas de la **Assistant projet (Game Installer)** , choisir le **informations de l’Application** lien.  
  
6.  Sur le **informations de l’Application** , spécifiez le nom de votre société que vous souhaitez qu’il apparaisse dans le programme d’installation. Vous pouvez utiliser votre propre nom de la société, ou pour cet exemple, utilisez **Contoso**. Spécifiez le nom de votre application ; Dans cet exemple, spécifiez **jeu**. Spécifiez l’adresse web de votre organisation ou pour cet exemple, utilisez **http://www.contoso.com**.  
  
7.  Au bas de la **Assistant projet (Game Installer)** , choisir le **Installation Interview** lien.  
  
8.  Sur le **Installation Interview** sous **vous souhaitez afficher une boîte de dialogue du contrat de licence**, sélectionnez le **non** case d’option. Sous **vous souhaitez inviter les utilisateurs à entrer leur nom de la société et le nom d’utilisateur**, sélectionnez le **non** case d’option.  
  
9. Dans **l’Explorateur de solutions**, développez le **Game Installer** de projet, développez le **planifier votre installation** nœud, puis ouvrez le **desinformationsgénérales** page.  
  
10. Sur le **des informations générales (Game Installer)** onglet dans la fenêtre d’éditeur, spécifiez un **ID de créateur de la balise**, par exemple, **regid.2012-12.com.Contoso**.  
  
11. Dans **l’Explorateur de solutions**, sous le **Game Installer** de projet, développez le **spécifiez les données d’Application** nœud, puis ouvrez le **fichiers** page.  
  
12. Sur le **fichiers (Game Installer)** onglet dans la fenêtre d’éditeur, sous **les fichiers de l’ordinateur Source**, ouvrez le menu contextuel pour **sortie principale de Game** et choisissez **Copie**.  
  
13. Ouvrir un menu contextuel dans l’espace sous le **nom** colonne **les fichiers de l’ordinateur de Destination**, puis choisissez **coller**. Un nouvel élément nommé **sortie de Game.Primary** s’affiche.  
  
14. Dans **l’Explorateur de solutions**, sous le **spécifiez les données d’Application** ouverture d’un nœud, le **redistribuables** page.  
  
15. Sur le **redistribuables (Game Installer)** onglet dans la fenêtre d’éditeur, sélectionnez le **Visual C++ 11.0 CRT (x86)** case à cocher.  
  
16. Dans la barre de menus, choisissez **générer**, **générer la Solution** pour générer le projet Game et le projet Game Installer.  
  
17. Dans le dossier de solution, recherchez le programme setup.exe qui a été généré à partir du programme Game Installer, puis lancez-le pour installer l’application Game sur votre ordinateur. Vous pouvez copier ce fichier pour installer l'application et ses fichiers de bibliothèques requis sur un autre ordinateur.  
  
18. Vous pouvez définir de nombreuses options dans le projet d’installation pour répondre à vos besoins. Pour plus d’informations, dans **l’Explorateur de solutions**, sous le **Game Installer** projet, ouvrez le **mise en route** page, puis choisissez la touche F1 pour ouvrir la bibliothèque d’aide ISLE.  
  
## <a name="next-steps"></a>Étapes suivantes  
 **Précédente :** [procédure pas à pas : débogage d’un projet (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)  
 [Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)