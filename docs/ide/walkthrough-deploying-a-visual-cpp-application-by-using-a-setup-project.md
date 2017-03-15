---
title: "Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ &#224; l&#39;aide d&#39;un projet d&#39;installation | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "déploiement pour Visual C++"
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ &#224; l&#39;aide d&#39;un projet d&#39;installation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit comment utiliser un projet d'installation pour déployer une application Visual C\+\+.  
  
## Composants requis  
 Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :  
  
-   Un ordinateur avec [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] installé.  
  
-   Un ordinateur supplémentaire qui n'a pas les bibliothèques Visual C\+\+.  
  
### Pour déployer une application à l'aide d'un projet d'installation  
  
1.  Utilisez l'**Assistant Application MFC** pour créer une nouvelle solution Visual Studio.  Pour rechercher l'Assistant, dans la boîte de dialogue **Nouveau projet**, développez le nœud **Visual C\+\+**, sélectionnez **MFC**, sélectionnez **Application MFC**, entrez un nom pour le projet, puis cliquez sur **OK**.  
  
2.  Modifiez la configuration de solution active en **Version finale**.  Dans le menu **Générer**, sélectionnez **Gestionnaire de configurations**.  Dans la boîte de dialogue **Gestionnaire de configurations**, sélectionnez **Version finale** dans la liste déroulante **Configuration de la solution active**.  
  
3.  Appuyez sur F7 pour générer l'application.  Ou, dans le menu **Générer**, cliquez sur **Générer la solution**.  Cela active le projet d'installation pour utiliser la sortie de ce projet d'application MFC.  
  
4.  Si vous ne l'avez pas déjà fait, téléchargez la version d'InstallShield Limited \(ÎLE\), qui est libre pour les développeurs Visual Studio et remplace les fonctionnalités des modèles de projet dans Visual Studio pour l'installation et le déploiement.  Lorsque vous êtes connecté à Internet, ouvrez la boîte de dialogue **Nouveau projet** en choisissant **Fichier**, **Nouveau**, **Projet** dans la barre de menus, ou en cliquant avec le bouton droit sur votre solution dans **Explorateur de solutions** et en choisissant **Ajouter**, **Nouveau projet…**.  Développez le nœud **Autres types de projets**, choisissez **Activer InstallShield Limited Edition** dans le nœud **Configuration et déploiement**, puis suivez les instructions qui s'affichent.  Une fois que vous avez téléchargé édition, installez et activé d'InstallShield Limited, fermez Visual Studio et rouvrez\-le.  
  
5.  Ouvrez la boîte de dialogue **Nouveau projet** de nouveau, développez le nœud **Autres types de projets**, puis choisissez **Projet d'édition d'InstallShield Limited** dans le nœud **Édition d'InstallShield Limited** .  
  
6.  Suivez les instructions dans le nœud **Mise en route** du projet d'installation créé par le modèle d'édition d'InstallShield Limited pour ajouter une référence de sortie à votre projet MFC Visual Studio.  
  
7.  Générez le projet d'installation pour créer un fichier d'installation \(setup.exe\).  Pour cela, cliquez avec le bouton droit sur le nœud du projet d'installation dans **Explorateur de solutions** et sélectionnez **Build**.  
  
     InstallShield Limited crée le fichier d'installation dans l'arborescence de projet d'installation \(par défaut, elle peut se trouver dans l'express\\le sous\-dossier SingleImage DiskImages\\\\ DISK1 du projet d'installation\).  
  
8.  Exécutez le programme d'installation sur un deuxième ordinateur qui ne dispose pas des bibliothèques Visual C\+\+.  
  
## Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)