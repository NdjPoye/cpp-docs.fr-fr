---
title: "Utilisation de contr&#244;les communs dans une bo&#238;te de dialogue | Microsoft Docs"
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
  - "contrôles communs (C++), dans des boîtes de dialogue"
  - "contrôles de boîte de dialogue (C++), contrôles communs"
  - "contrôles Windows communs (C++), dans des boîtes de dialogue"
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de contr&#244;les communs dans une bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles communs Windows peuvent être utilisés dans des [boîtes de dialogue](../mfc/dialog-boxes.md), les modes formulaire, les vues des enregistrements, et toute autre fenêtre selon un modèle de boîte de dialogue.  La procédure suivante, avec quelques modifications mineures, fonctionne pour les formes.  
  
## Procédures  
  
#### Utiliser un contrôle commun dans une boîte de dialogue  
  
1.  Localisez le contrôle dans le modèle de boîte de dialogue [utilisation de l'éditeur de boîtes de dialogue](../mfc/using-the-dialog-editor-to-add-controls.md).  
  
2.  Ajoutez une variable membre qui représente le contrôle à une classe de boîte de dialogue.  Dans la boîte de dialogue **Ajouter une variable membre**, vérifiez **Variable du contrôle** et vérifiez que **Contrôler** est sélectionné pour la **Catégorie**.  
  
3.  Si ce contrôle commun fournit des données au programme, déclarez la variable membre supplémentaire dans la classe de la boîte de dialogue pour gérer les valeurs d'entrée.  
  
    > [!NOTE]
    >  Vous pouvez ajouter ces variables membres à l'aide du menu contextuel dans Affichage de classes \(voir [Ajouter une variable membre](../ide/adding-a-member-variable-visual-cpp.md)\).  
  
4.  Dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md) pour votre classe de boîte de dialogue, définissez des conditions initiales pour le contrôle commun.  Utilisation de la variable membre créée à l'étape précédente, utilisez les fonctions membres pour définir la valeur initiale et d'autres paramètres.  Consultez les descriptions suivantes des contrôles pour plus d'informations sur les paramètres.  
  
     Vous pouvez également utiliser [échange de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md) \(DDX\) pour initialiser des contrôles dans une boîte de dialogue.  
  
5.  Dans les gestionnaires des contrôles dans la boîte de dialogue, utilisez la variable membre pour manipuler le contrôle.  Consultez les descriptions suivantes des contrôles pour plus d'informations sur les méthodes.  
  
    > [!NOTE]
    >  La variable membre existera uniquement tant que la boîte de dialogue existe.  Vous ne pouvez pas interroger le contrôle sur les valeurs d'entrée après que la boîte de dialogue a été fermée.  Pour utiliser des valeurs d'entrée d'un contrôle commun, substituez `OnOK` dans la classe de la boîte de dialogue.  Dans votre fichier, interrogez le contrôle des valeurs d'entrée et stockez les valeurs des variables membres des classes de boîte de dialogue.  
  
    > [!NOTE]
    >  Vous pouvez également utiliser l'échange de données de boîtes de dialogue pour définir et récupérer des valeurs de contrôles dans une boîte de dialogue.  
  
## Remarques  
 L'ajout des contrôles communs à une boîte de dialogue entraîne le non fonctionnement de la boîte de dialogue.  Reportez\-vous à [Adding Controls to a Dialog Causes the Dialog to No Longer Function](../mfc/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) pour plus d'informations sur la gestion de cette situation.  
  
## Que voulez\-vous faire ?  
  
-   [Ajouter des contrôles dans une boîte de dialogue à la main plutôt qu'avec l'éditeur boîtes de dialogue](../mfc/adding-controls-by-hand.md)  
  
-   [Dériver mon contrôle de l'un des contrôles communs Windows standard](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Utilisation d'un contrôle commun en tant que fenêtre enfant](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Recevoir les messages de notification d'un contrôle](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Échange de données de boîtes de dialogue \(DDX\)](../mfc/dialog-data-exchange-and-validation.md)  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)