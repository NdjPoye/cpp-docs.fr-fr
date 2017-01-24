---
title: "Cr&#233;ation d&#39;un contr&#244;le ActiveX MFC | Microsoft Docs"
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
  - "vc.appwiz.activex.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), créer"
  - "contrôles ActiveX MFC (C++), créer"
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un contr&#244;le ActiveX MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les programmes de création de contrôles ActiveX sont des programmes modulaires conçus pour ajouter un type spécifique de fonctionnalité à une application parente.  Par exemple, vous pouvez créer un contrôle de type bouton pour une utilisation dans une boîte de dialogue ou un contrôle de type barre d'outils destiné à une page Web.  
  
 L'utilisation de l'[Assistant Contrôle ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md) constitue le moyen le plus rapide de créer un contrôle ActiveX MFC.  
  
### Pour créer un contrôle ActiveX MFC à l'aide de l'Assistant Contrôle ActiveX MFC  
  
1.  Suivez les instructions de la rubrique d'aide [Création d'un projet à l'aide d'un Assistant Application Visual C\+\+](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sélectionnez l'icône **Contrôle ActiveX MFC** dans le volet Modèles pour démarrer l'Assistant Contrôle ActiveX MFC.  
  
3.  À l'aide de l'Assistant, définissez les [paramètres de l'application](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), les [noms du contrôle](../../mfc/reference/control-names-mfc-activex-control-wizard.md) et les [paramètres du contrôle](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) souhaités.  
  
    > [!NOTE]
    >  Ignorez cette étape afin que l'Assistant conserve les paramètres par défaut.  
  
4.  Cliquez sur **Terminer** pour fermer l'Assistant et ouvrir votre nouveau projet dans l'environnement de développement.  
  
 Une fois votre projet créé, tous les nouveaux fichiers sont affichés dans l'**Explorateur de solutions**.  Pour plus d'informations sur les fichiers créés par l'Assistant pour votre projet, consultez le fichier Readme.txt généré pour le projet.  Pour plus d'informations sur les types de fichiers, consultez [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
 Après avoir créé votre projet, vous pouvez y ajouter des [fonctions](../../ide/add-member-function-wizard.md), des [variables](../../ide/add-member-variable-wizard.md), des [événements](../../ide/add-event-wizard.md), des [propriétés](../../ide/names-add-property-wizard.md) et des [méthodes](../../ide/add-method-wizard.md) en utilisant les Assistants Code.  Pour plus d'informations sur la personnalisation d'un contrôle ActiveX, consultez [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md).  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Deploying Applications](http://msdn.microsoft.com/fr-fr/4ff8881d-0daf-47e7-bfe7-774c625031b4)