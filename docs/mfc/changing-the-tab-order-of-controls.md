---
title: "Changing the Tab Order of Controls | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "controls [C++], tab order"
  - "focus, tab order"
  - "tab controls, tab order"
  - "Tabstop property for controls"
  - "controls [C++], focus"
  - "dialog box controls, tab order"
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Tab Order of Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'ordre de tabulation est l'ordre en fonction duquel le focus d'entrée se déplace d'un contrôle à l'autre dans une boîte de dialogue lorsque vous appuyez sur la touche TABULATION.  En règle générale, l'ordre de tabulation est défini de gauche à droite et de haut en bas dans une boîte de dialogue.  Chaque contrôle dispose d'une propriété **Tabstop** qui détermine si un contrôle reçoit le focus d'entrée.  
  
### Pour définir le focus d'entrée pour un contrôle  
  
1.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), sélectionnez **True** ou **False** dans la propriété **Tabstop**.  
  
 Même les contrôles dont la propriété Tabstop n'a pas la valeur True doivent faire partie de l'ordre de tabulation.  Cela est important, par exemple, lorsque vous [définissez des touches d'accès rapide \(mnémoniques\)](../mfc/defining-mnemonics-access-keys.md) pour les contrôles qui n'ont pas de légende.  Le texte statique qui contient une touche d'accès rapide pour un contrôle associé doit immédiatement précéder le contrôle associé dans l'ordre de tabulation.  
  
> [!NOTE]
>  Si votre boîte de dialogue contient des contrôles superposés, la modification de l'ordre de tabulation peut changer la façon dont les contrôles sont affichés.  Les contrôles qui viennent ensuite dans l'ordre de tabulation sont toujours affichés au\-dessus des contrôles superposés qui les précèdent dans l'ordre de tabulation.  
  
#### Pour afficher l'ordre de tabulation actuel pour tous les contrôles d'une boîte de dialogue  
  
1.  Dans le menu **Format**, cliquez sur **Ordre de tabulation**.  
  
 \- ou \-  
  
-   Appuyez sur CTRL \+ D.  
  
#### Pour changer l'ordre de tabulation pour tous les contrôles d'une boîte de dialogue  
  
1.  Dans le menu **Format**, cliquez sur **Ordre de tabulation**.  
  
     Un chiffre dans le coin supérieur gauche de chaque contrôle affiche sa place dans l'ordre de tabulation actuel.  
  
2.  Définissez l'ordre de tabulation en cliquant sur chaque contrôle dans l'ordre que doit suivre la touche TABULATION.  
  
3.  Appuyez sur **ENTRÉE** pour quitter le mode **Ordre de tabulation**.  
  
    > [!TIP]
    >  Lorsque vous êtes en mode Ordre de tabulation, vous pouvez appuyer sur ÉCHAP ou sur ENTRÉE pour désactiver la possibilité de changer l'ordre de tabulation.  
  
#### Pour changer l'ordre de tabulation pour plusieurs contrôles  
  
1.  Dans le menu **Format**, cliquez sur **Ordre de tabulation**.  
  
2.  Spécifiez où l'ordre doit commencer à changer.  Pour ce faire, maintenez la touche **CTRL** enfoncée et cliquez sur le contrôle qui précède celui à partir duquel vous souhaitez modifier l'ordre.  
  
     Par exemple, si vous souhaitez changer l'ordre des contrôles 7 à 9, maintenez la touche CTRL enfoncée, puis sélectionnez en premier le contrôle 6.  
  
    > [!NOTE]
    >  Pour attribuer la valeur 1 à un contrôle spécifique \(premier dans l'ordre de tabulation\), double\-cliquez sur le contrôle.  
  
3.  Relâchez la touche CTRL, puis cliquez sur les contrôles dans l'ordre de tabulation souhaité à partir de ce contrôle.  
  
4.  Appuyez sur **ENTRÉE** pour quitter le mode **Ordre de tabulation**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 Win32  
  
## Voir aussi  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)