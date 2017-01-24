---
title: "Testing a Dialog Box | Microsoft Docs"
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
  - "Test Dialog command"
  - "testing, dialog boxes"
  - "dialog boxes, testing"
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Testing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez une boîte de dialogue, vous pouvez simuler et tester son comportement au moment de l’exécution sans compiler votre programme. Dans ce mode, vous pouvez :  
  
-   Taper du texte, effectuer des sélections dans des listes de zone de liste déroulante, activer ou désactiver des options, et choisir des commandes  
  
-   Tester l’ordre de tabulation  
  
-   Tester le groupement des contrôles tels que les cases à cocher et les cases d’option  
  
-   Tester les raccourcis clavier pour les contrôles dans la boîte de dialogue  
  
    > [!NOTE]
    >  Les connexions au code de boîte de dialogue effectuées à l’aide des Assistants ne sont pas incluses dans la simulation.  
  
 Quand vous testez une boîte de dialogue, elle s’affiche généralement à un emplacement qui est relatif à la fenêtre principale du programme. Si vous avez affecté la valeur True à la propriété Absolute Align de la boîte de dialogue, celle\-ci s’affiche à une position relative au coin supérieur gauche de l’écran.  
  
### Pour tester une boîte de dialogue  
  
1.  Lorsque l’Éditeur de boîtes de dialogue est la fenêtre active, dans la barre de menus, choisissez **Format**, **Tester la boîte de dialogue**.  
  
2.  Pour arrêter la simulation, appuyez sur Échap ou sélectionnez simplement le bouton **Fermer** dans la boîte de dialogue que vous testez.  
  
 Pour plus d’informations sur la façon d’ajouter des ressources aux projets managés, consultez [Ressources dans des applications de bureau](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
 Spécifications  
  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)   
 [Affichage ou masquage de la barre d’outils Éditeur de boîtes de dialogue](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)