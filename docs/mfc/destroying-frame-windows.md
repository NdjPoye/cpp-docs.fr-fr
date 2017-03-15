---
title: "Destruction des fen&#234;tres frame | Microsoft Docs"
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
  - "PostNcDestroy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Default (méthode)"
  - "détruire des fenêtres frame"
  - "DestroyWindow (méthode)"
  - "fenêtres frame de document, détruire"
  - "fenêtres frame (C++), détruire"
  - "MFC (C++), fenêtres frame"
  - "OnClose (méthode)"
  - "OnNcDestroy (méthode), et fenêtres frame"
  - "PostNcDestroy (méthode)"
  - "fenêtres (C++), détruire"
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Destruction des fen&#234;tres frame
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'infrastructure MFC gère la destruction de la fenêtre ainsi que la création de ces fenêtres associées à l'infrastructure de documents et les vues.  Si vous créez des fenêtres supplémentaires, vous devez vous charger de les détruire.  
  
 Dans l'infrastructure, lorsque l'utilisateur ferme le cadre de la fenêtre, le gestionnaire par défaut d' [OnClose](../Topic/CWnd::OnClose.md) de la fenêtre appelle [DestroyWindow](../Topic/CWnd::DestroyWindow.md).  La dernière fonction membre appelée lorsque la fenêtre Windows est détruite est [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), qui effectue un peu de nettoyage, appelle la fonction membre d' [Par défaut](../Topic/CWnd::Default.md) pour effectuer le nettoyage Windows, et enfin appelle la fonction membre [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md)virtuelle.  L'implémentation d' [CFrameWnd](../mfc/reference/cframewnd-class.md) d' `PostNcDestroy` supprime l'objet de fenêtre C\+\+.  Vous ne devez jamais utiliser l'opérateur C\+\+ **supprimer** sur une fenêtre cadre.  Utilisez plutôt `DestroyWindow`.  
  
 Lorsque la fenêtre principale se ferme, l'application se ferme.  S'il existe des documents non être modifiés, l'infrastructure affiche un message pour demander si les documents stockés et garantit que les documents appropriés sont enregistrés si nécessaire.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Création de fenêtres de cadre de document](../mfc/creating-document-frame-windows.md)  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)