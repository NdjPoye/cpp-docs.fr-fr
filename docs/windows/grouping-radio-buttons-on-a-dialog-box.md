---
title: "Grouping Radio Buttons on a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.grouping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "member variables, adding to radio button groups"
  - "variables, dialog box control member variables"
  - "dialog box controls, grouping radio buttons"
  - "grouping controls"
  - "radio buttons, grouping on dialog boxes"
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Grouping Radio Buttons on a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous ajoutez des cases d’option à une boîte de dialogue, traitez\-les comme un groupe en définissant une propriété Groupe dans la fenêtre Propriétés du premier bouton du groupe. Un ID de contrôle pour cette case d’option apparaît alors dans [Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md), ce qui vous permet d’ajouter une variable membre pour le groupe de cases d’option.  
  
 Vous pouvez ajouter plusieurs groupes de cases d’option à une boîte de dialogue. Pour ajouter chaque groupe, appliquez la procédure suivante.  
  
### Pour ajouter un groupe de cases d’option à une boîte de dialogue  
  
1.  Sélectionnez le contrôle de case d’option dans la fenêtre [Boîte à outils](../Topic/Toolbox.md) et cliquez sur l’emplacement dans la boîte de dialogue où vous souhaitez placer le contrôle.  
  
2.  Répétez l’étape 1 pour ajouter autant de cases d’option que vous le souhaitez. Assurez\-vous que les cases d’option du groupe se suivent dans l’ordre de tabulation \(pour plus d’informations, consultez [Modification de l’ordre de tabulation des contrôles](../mfc/changing-the-tab-order-of-controls.md)\).  
  
3.  Dans la fenêtre [Propriétés](../Topic/Properties%20Window.md), affectez la valeur **True** à la propriété **Groupe** de la *première* case d’option dans l’ordre de tabulation.  
  
     L’affectation de la valeur **True** à la propriété **Groupe** ajoute le style WS\_GROUP à l’entrée du bouton dans l’objet de boîte de dialogue du script de ressources et permet de s’assurer qu’un utilisateur ne peut sélectionner qu’une case d’option à la fois dans le groupe de boutons \(quand l’utilisateur clique sur une case d’option, les autres cases dans le groupe sont désactivées\).  
  
    > [!NOTE]
    >  La propriété **Groupe** de la première case d’option du groupe doit avoir la valeur **True**. Si vous avez d’autres contrôles qui ne font pas partie du groupe de cases d’option, affectez aussi la valeur **True** à la propriété **Groupe** du premier contrôle *qui est en dehors du groupe*. Vous pouvez rapidement identifier le premier contrôle en dehors du groupe en appuyant sur Ctrl\+D pour afficher l’ordre de tabulation.  
  
### Pour ajouter une variable membre pour le groupe de cases d’option  
  
1.  Cliquez avec le bouton droit sur le premier contrôle de case d’option dans l’ordre de tabulation \(le contrôle dominant et celui dont la propriété **Groupe** a la valeur True\).  
  
2.  Choisissez **Ajouter une variable** dans le menu contextuel.  
  
3.  Dans l’[Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md), cochez la case **Variable de contrôle**, puis sélectionnez la case d’option **Valeur**.  
  
4.  Dans la zone **Nom de la variable**, tapez un nom pour la nouvelle variable membre.  
  
5.  Dans la zone de liste **Type de variable**, sélectionnez **int** ou tapez **int**.  
  
6.  Vous pouvez maintenant modifier votre code pour spécifier la case d’option qui doit apparaître sélectionnée. Par exemple, m\_radioBox1 \= 0; sélectionne la première case d’option du groupe.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)