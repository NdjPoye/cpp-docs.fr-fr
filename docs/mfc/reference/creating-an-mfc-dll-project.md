---
title: "Cr&#233;ation d&#39;un projet DLL MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcdll.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), créer"
  - "DLL (C++), MFC"
  - "DLL MFC (C++), créer des projets"
  - "projets (C++), créer"
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un projet DLL MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une DLL MFC est un fichier binaire qui joue le rôle d'une bibliothèque partagée de fonctions pouvant être utilisée par plusieurs applications en même temps.  La façon la plus simple de créer un projet DLL MFC est d'utiliser l'Assistant DLL MFC.  
  
> [!NOTE]
>  L'apparence des fonctionnalités dans l'environnement IDE peut dépendre de votre édition ou de vos paramètres actifs, et peut différer de celle décrite dans l'aide.  Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils**.  Pour plus d'informations, consultez [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/fr-fr/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Pour créer un projet DLL MFC en utilisant l'Assistant DLL MFC  
  
1.  Suivez les instructions de la rubrique d'aide [Création d'un projet à l'aide d'un Assistant Application Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Remarque** Dans la boîte de dialogue **Nouveau projet**, sélectionnez l'icône `MFC DLL` dans le volet Modèles pour ouvrir l'Assistant DLL MFC.  
  
1.  Définissez les paramètres de votre application en utilisant la page [Paramètres de l'application](../../mfc/reference/application-settings-mfc-dll-wizard.md) de l'[Assistant DLL MFC](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Ignorez cette étape afin que l'Assistant conserve les paramètres par défaut.  
  
2.  Cliquez sur **Terminer** pour fermer l'Assistant et ouvrir votre nouveau projet dans l'**Explorateur de solutions**.  
  
 Une fois votre projet créé, vous pouvez afficher les fichiers créés dans l'Explorateur de solutions.  Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet.  Pour plus d'informations sur les types de fichiers, consultez [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## Voir aussi  
 [Types de projets Visual C\+\+](../Topic/Debugging%20Preparation:%20Visual%20C++%20Project%20Types.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/fr-fr/4ff8881d-0daf-47e7-bfe7-774c625031b4)