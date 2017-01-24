---
title: "Substitution d&#39;une fonction virtuelle (Visual C++) | Microsoft Docs"
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
  - "vc.codewiz.virtualfunc.override"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de base, substituer des fonctions virtuelles définies dans des"
  - "Propriétés (fenêtre), substituer des fonctions virtuelles dans"
  - "fonctions virtuelles, substituer"
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Substitution d&#39;une fonction virtuelle (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez substituer les fonctions virtuelles définies dans une classe de base à partir de la [fenêtre Propriétés](../Topic/Properties%20Window.md) de Visual Studio.  
  
### Pour substituer une fonction virtuelle dans la fenêtre Propriétés  
  
1.  Dans l'affichage de classes, cliquez sur la classe  
  
2.  Dans la fenêtre Propriétés, cliquez sur le bouton **Substitutions**.  
  
    > [!NOTE]
    >  Le bouton **Substitutions** est disponible si vous sélectionnez le nom de la classe dans l'affichage de classes ou si vous cliquez à l'intérieur de la fenêtre source.  
  
     La colonne de gauche énumère les fonctions virtuelles.  Si le nom d'une fonction virtuelle s'affiche également dans la colonne de droite, une substitution a déjà été implémentée.  
  
3.  Si aucune substitution n'est prévue pour la fonction, cliquez sur la cellule de la colonne de droite de la fenêtre Propriétés afin d'afficher le nom proposé pour la fonction redéfinie, indiqué au format suivant : \<add\>*FuncName*.  
  
4.  Cliquez sur le nom proposé pour ajouter le code stub pour la fonction.  
  
5.  Pour modifier une fonction de substitution, double\-cliquez sur le nom de la fonction dans l'affichage de classes et modifiez le code dans la fenêtre source.  
  
 Pour supprimer une substitution, cliquez sur la fonction de substitution dans la colonne de droite et sélectionnez \<delete\>*FuncName*.  Le code de la fonction est transformé en commentaires.  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC, gestionnaire de messages](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)