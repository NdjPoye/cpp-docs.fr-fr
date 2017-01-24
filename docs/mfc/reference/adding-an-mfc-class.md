---
title: "Ajout d&#39;une classe MFC | Microsoft Docs"
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
  - "vc.codewiz.classes.adding.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), ajouter MFC"
  - "MFC, ajouter des classes"
ms.assetid: 9a96b67f-40bf-43d4-8872-2f8dfc5404f1
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une classe MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour ajouter à votre projet des classes dérivées des classes de la bibliothèque MFC \(Microsoft Foundation Class\), utilisez la commande **Ajouter une classe** disponible dans l'[Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  Spécifiez le nom de la nouvelle classe, sélectionnez la classe de base et l'ID de la boîte de dialogue à laquelle elle est associée \(le cas échéant\).  L'Assistant Code crée un fichier d'en\-tête et un fichier d'implémentation, puis les ajoute à votre projet.  
  
> [!NOTE]
>  Vous pouvez ajouter des classes MFC à une application COM ATL si vous avez à l'origine [créé l'application avec la prise en charge MFC](../../atl/reference/mfc-support-in-atl-projects.md).  Il est également possible d'ajouter des classes MFC à des projets Win32 prenant en charge MFC.  
  
### Pour ajouter une classe MFC à votre projet  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le nom du projet.  Cliquez sur **Ajouter**, puis sur **Ajouter une classe** pour ouvrir la boîte de dialogue [Ajouter une classe](../../ide/add-class-dialog-box.md).  
  
2.  Dans le volet Modèles, sélectionnez **Classe MFC** et appuyez sur le bouton **Ajouter**.  
  
3.  Définissez les paramètres de la nouvelle classe dans la boîte de dialogue [Assistant Classe MFC](../../mfc/reference/mfc-add-class-wizard.md).  
  
4.  Cliquez sur **Terminer** pour fermer l'Assistant et afficher la nouvelle classe dans l'Affichage de classes.  Vous pouvez également afficher les fichiers créés par l'Assistant dans l'**Explorateur de solutions**.  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Vue d'ensemble des classes](../../mfc/class-library-overview.md)