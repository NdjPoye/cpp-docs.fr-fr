---
title: "Ajout de contr&#244;les manuellement | Microsoft Docs"
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
  - "contrôles communs (C++), ajouter"
  - "contrôler le focus d'entrée"
  - "contrôles (MFC), ajouter aux boîtes de dialogue"
  - "contrôles de boîte de dialogue (C++), ajouter aux boîtes de dialogue"
  - "focus, contrôler l'entrée"
  - "contrôle du focus d'entrée"
  - "contrôles Windows communs (C++), ajouter"
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout de contr&#244;les manuellement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez soit [ajouter des contrôles dans une boîte de dialogue à l'aide de l'éditeur de boîtes de dialogue](../mfc/using-the-dialog-editor-to-add-controls.md) ou les ajouter vous, avec du code.  
  
 Pour créer un objet de contrôle, vous incluerez généralement l'objet de contrôle C\+\+ dans une boîte de dialogue C\+\+ ou un objet cadre de fenêtre.  Comme de nombreux autres objets dans l'infrastructure, les vérifications nécessitent la construction sur deux niveaux.  Vous devriez appeler la fonction membre **Créer** du contrôle comme une partie de la création de la boîte de dialogue parente ou la fenêtre de cadre.  Pour les boîtes de dialogue, ceci est généralement effectuée dans [OnInitDialog](../Topic/CDialog::OnInitDialog.md), et pour les fenêtres de cadre, dans [OnCreate](../Topic/CWnd::OnCreate.md).  
  
 L'exemple suivant montre comment vous pouvez déclarer un objet `CEdit` dans la déclaration de classe d'une classe de la boîte de dialogue dérivée puis appeler la fonction membre **Créer** dans `OnInitDialog`.  Comme l'objet de `CEdit` est déclaré comme un objet incorporé, il est automatiquement construit lorsque l'objet de dialogue est créé, mais il doit être néanmoins initialisé avec sa propre fonction membre **Créer**.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/CPP/adding-controls-by-hand_1.h)]  
  
 La fonction suivante `OnInitDialog` configure un rectangle, puis appelle **Créer** pour créer le contrôle d'édition windows et le joindre à l'objet non initialisé de `CEdit`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/CPP/adding-controls-by-hand_2.cpp)]  
  
 Après avoir créé l'objet de modification, vous pouvez également définir le focus d'entrée au contrôle en appelant la fonction membre `SetFocus`.  Enfin, vous retournez 0 depuis `OnInitDialog` pour indiquer que vous définissez le focus.  Si vous retournez une valeur différente de zéro, le gestionnaire de dialogue définit le focus sur le premier élément de contrôle dans la liste des éléments de dialogue.  Dans la plupart des cas, vous souhaiterez ajouter des contrôles dans les boîtes de dialogue de l'éditeur de boîtes de dialogue.  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)