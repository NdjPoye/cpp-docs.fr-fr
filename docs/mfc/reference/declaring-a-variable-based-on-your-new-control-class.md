---
title: "D&#233;claration d&#39;une variable bas&#233;e sur votre nouvelle classe de contr&#244;le | Microsoft Docs"
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
  - "vc.codewiz.classes.control.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), déclarer des variables basées sur"
  - "classes de contrôle, variables"
  - "variables, classes de contrôle"
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;claration d&#39;une variable bas&#233;e sur votre nouvelle classe de contr&#244;le
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous avez créé une classe de contrôle MFC, vous pouvez déclarer une variable qui se base sur celle\-ci.  Pour fournir un contexte à la nouvelle variable, vous devez ouvrir l'Éditeur de boîtes de dialogue et modifier la boîte de dialogue dans laquelle vous souhaitez employer le contrôle réutilisable.  Par ailleurs, une classe doit déjà être associée à la boîte de dialogue.  Pour plus d'informations sur l'utilisation de l'Éditeur de boîtes de dialogue, consultez [Éditeur de boîtes de dialogue](../../mfc/dialog-editor.md).  
  
### Pour déclarer une variable basée sur votre classe réutilisable  
  
1.  Lorsque vous modifiez la boîte de dialogue, faites glisser un contrôle, du même type que la classe de base de votre nouveau contrôle, de la barre d'outils Contrôles jusqu'à la boîte de dialogue.  
  
2.  Placez le pointeur de la souris sur le contrôle que vous venez de déplacer.  
  
3.  Appuyez sur la touche CTRL et double\-cliquez sur le contrôle.  
  
     La boîte de dialogue [Ajouter une variable de membre](../../ide/add-member-variable-wizard.md) s'affiche.  
  
4.  Dans la zone **Accès**, sélectionnez l'accès correct pour votre contrôle.  
  
5.  Activez la case à cocher **Variable du contrôle**.  
  
6.  Dans la zone **Nom de la variable**, tapez un nom.  
  
7.  Sous **Catégorie**, cliquez sur **Contrôle**.  
  
8.  Dans la liste **ID de contrôle**, sélectionnez le contrôle que vous avez ajouté.  La liste **Type de variable** affiche le type de variable correct et la zone **Type de contrôle**, le type de contrôle correct.  
  
9. Dans la zone **Commentaire**, ajoutez les commentaires éventuels qui doivent figurer dans votre code.  
  
10. Cliquez sur **OK**.  
  
## Voir aussi  
 [Mappage de messages à des fonctions](../../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)