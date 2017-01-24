---
title: "Cr&#233;ation d&#39;une application MFC | Microsoft Docs"
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
  - "applications (MFC)"
  - "MFC [C++], créer des applications"
  - "applications MFC"
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une application MFC est une application exécutable pour Windows qui se base sur la bibliothèque MFC \(Microsoft Foundation Class\).  L'utilisation de l'Assistant Application MFC constitue le moyen le plus facile pour créer une application MFC.  
  
> [!IMPORTANT]
>  Les projets MFC ne sont pas pris en charge dans les éditions Visual Studio Express.  
  
 Les exécutables MFC se décomposent généralement en cinq types : les applications Windows standard, les boîtes de dialogue, les applications basées sur les formulaires, les applications de style Explorateur et les applications de style navigateur Web.  Pour plus d'informations, consultez :  
  
-   [Utilisation des classes pour l'écriture d'applications Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)  
  
-   [Création et affichage de boîtes de dialogue](../../mfc/creating-and-displaying-dialog-boxes.md)  
  
-   [Création d'une application MFC basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [Création d'une application MFC de style Explorateur de fichiers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)  
  
-   [Création d'une application MFC de style navigateur Web](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)  
  
 L'Assistant Application MFC génère les classes et fichiers appropriés pour n'importe lequel de ces types d'applications, en fonction des options sélectionnées dans l'Assistant.  
  
### Pour créer une application MFC à l'aide de l'Assistant Application MFC  
  
1.  Suivez les instructions de la rubrique d'aide [Création d'un projet à l'aide d'un Assistant Application Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sélectionnez **Application MFC** dans le volet Modèles pour ouvrir l'Assistant.  
  
3.  Définissez les paramètres de l'application à l'aide de l'[Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md).  
  
    > [!NOTE]
    >  Ignorez cette étape afin que l'Assistant conserve les paramètres par défaut.  
  
4.  Cliquez sur **Terminer** pour fermer l'Assistant et ouvrir votre nouveau projet dans l'environnement de développement.  
  
 Une fois votre projet créé, vous pouvez visualiser les fichiers créés dans l'**Explorateur de solutions**.  Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet.  Pour plus d'informations sur les types de fichiers, consultez [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## Voir aussi  
 [Debugging Preparation: Visual C\+\+ Windows Applications](http://msdn.microsoft.com/fr-fr/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/fr-fr/4ff8881d-0daf-47e7-bfe7-774c625031b4)