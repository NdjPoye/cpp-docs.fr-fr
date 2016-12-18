---
title: "Defining Mnemonics (Access Keys) | Microsoft Docs"
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
  - "access keys [C++], adding"
  - "keyboard shortcuts [C++], controls"
  - "dialog box controls, mnemonics"
  - "access keys [C++], checking"
  - "mnemonics, checking for duplicate"
  - "mnemonics"
  - "mnemonics, dialog box controls"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "Check Mnemonics command"
  - "controls [C++], access keys"
  - "access keys [C++]"
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Mnemonics (Access Keys)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En règle générale, les utilisateurs du clavier déplacent le focus d'un contrôle à l'autre dans la boîte de dialogue à l'aide des touches de direction ou de la touche TABULATION.  Cependant, vous pouvez définir une touche d'accès rapide \(un nom mnémonique ou facile à retenir\) qui permet aux utilisateurs de choisir un contrôle en appuyant sur une seule touche.  
  
### Pour définir une touche d'accès rapide pour un contrôle avec une légende visible \(boutons de commande, cases à cocher et cases d'option\)  
  
1.  Sélectionnez le contrôle dans la boîte de dialogue.  
  
2.  Dans la [fenêtre Propriétés](../Topic/Properties%20Window.md), dans la propriété **Caption**, tapez un nouveau nom pour le contrôle en tapant un **&** devant la lettre que vous souhaitez utiliser comme touche d'accès rapide pour ce contrôle.  Par exemple, `&Radio1`.  
  
3.  Appuyez sur **Entrée**.  
  
     La touche d'accès rapide s'affiche soulignée dans la légende, par exemple, **R**adio1.  
  
### Pour définir une touche d'accès rapide pour un contrôle sans légende visible  
  
1.  Créez une légende pour le contrôle en utilisant un contrôle **Static Text** dans la [Boîte à outils](../Topic/Toolbox.md).  
  
2.  Dans la légende de texte statique, tapez un **&** devant la lettre que vous souhaitez utiliser comme touche d'accès rapide.  
  
3.  Assurez\-vous que le contrôle de texte statique précède immédiatement dans l'ordre de tabulation le contrôle qu'il identifie.  
  
 Toutes les touches d'accès rapide de la boîte de dialogue doivent être uniques.  
  
#### Pour contrôler les touches d'accès rapide dupliquées  
  
1.  Dans le menu **Format**, cliquez sur **Vérifier les mnémoniques**.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l'ajout de fichiers de ressources aux projets managés, l'accès aux ressources, l'affichage de ressources statiques et l'assignation de chaînes de ressources aux propriétés, et ce manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Configuration requise  
 Win32  
  
## Voir aussi  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)