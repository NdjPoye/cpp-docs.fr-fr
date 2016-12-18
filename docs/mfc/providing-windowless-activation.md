---
title: "Mise &#224; disposition de l&#39;activation sans fen&#234;tre | Microsoft Docs"
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
  - "activation (C++), contrôles ActiveX MFC"
  - "activation (C++), sans fenêtre"
  - "contrôles ActiveX MFC (C++), options d'activation"
  - "activation sans fenêtre des contrôles ActiveX MFC"
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise &#224; disposition de l&#39;activation sans fen&#234;tre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le code de conception de la fenêtre \(autrement dit, tout ce qui se produit lorsque vous appelez **CreateWindow**\) est coûteux à exécuter.  Un contrôle qui gère une fenêtre affichée à l'écran doit gérer les messages de la fenêtre.  Les contrôles sans fenêtre sont donc plus rapides que les contrôles avec fenêtre.  
  
 Un autre avantage des contrôles sans fenêtre est que, contrairement aux contrôles fenêtrés, les contrôles sans fenêtre prennent en charge la peinture transparente et les régions d'affichage non\-rectangulaires.  Un exemple classique d'un contrôle transparent est un contrôle de texte avec un arrière\-plan transparent.  Les contrôles peignent le texte mais pas l'arrière\-plan, ainsi tout ce qui est sous le texte transparaît.  De nouvelles formes utilisent souvent des contrôles non\-rectangulaires, tels que les flèches et les boutons arrondis.  
  
 Souvent, un contrôle n'a pas besoin d'avoir sa propre fenêtre et, en revanche, peut utiliser les services de fenêtre de son conteneur, à condition que le conteneur ait été écrit pour prendre en charge les objets sans fenêtre.  Les contrôles sans fenêtre sont à compatibilité descendante avec les conteneurs plus anciens.  Dans les conteneurs anciens et non écrits pour prendre en charge les contrôles sans fenêtre, les contrôles sans fenêtre crée une fenêtre lorsqu'ils sont actifs.  
  
 Les contrôles sans fenêtre n'ont pas leurs propres fenêtres, le conteneur \(qui lui possède une fenêtre\) est chargé de fournir des services qui auraient sinon été fournis par la propre fenêtre du contrôle.  Par exemple, si votre contrôle a besoin d'interroger le focus clavier, d'intercepter la souris, ou d'obtenir le contexte de périphérique, ces opérations sont gérées par le conteneur.  Le conteneur achemine les messages d'entrée utilisateur envoyés dans la fenêtre au contrôle sans fenêtre approprié, à l'aide de l'interface `IOleInPlaceObjectWindowless`. \(Voir *ActiveX Kit de développement logiciel* \(SDK\) pour une description de cette interface.\) Des fonctions membres de `COleControl` appelent ces services du conteneur.  
  
 Pour faire en sorte que votre contrôle utilise l'activation sans fenêtre, incluez l'indicateur de **windowlessActivate** dans l'ensemble des balises retournées par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Par exemple :  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/CPP/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-windowless-activation_3.cpp)]  
  
 Le code pour inclure cet indicateur est automatiquement généré si vous sélectionnez l'option de **Activation sans fenêtre** dans la page d' [Paramètres du contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md) de l'Assistant Contrôle ActiveX MFC.  
  
 Lorsque l'activation sans fenêtre est activée, le conteneur délèguera les messages d'entrée à l'interface `IOleInPlaceObjectWindowless` du contrôle.  l'implémentation de `COleControl`de cette interface répartit les messages via la table des messages de votre contrôle, après avoir analysé les coordonnées de la souris correctement.  Vous pouvez traiter les messages comme des messages ordinaires de fenêtre, en ajoutant des entrées correspondantes dans la table des messages.  Dans les gestionnaires de ces messages, évitez d'utiliser la variable membre `m_hWnd` \(ou une fonction membre qui utilise\) sans vérifier d'abord que la valeur n'est pas **NULL**.  
  
 `COleControl` fournit les fonctions membres qui appellent la capture de la souris, le focus clavier, le défilement, et d'autres services de la fenêtre du conteneur selon le cas, notamment :  
  
-   [GetFocus](../Topic/COleControl::GetFocus.md), [SetFocus](../Topic/COleControl::SetFocus.md)  
  
-   [GetCapture](../Topic/COleControl::GetCapture.md), [SetCapture](../Topic/COleControl::SetCapture.md), [ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)  
  
-   [GetDC](../Topic/COleControl::GetDC.md), [ReleaseDC](../Topic/COleControl::ReleaseDC.md)  
  
-   [InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)  
  
-   [ScrollWindow](../Topic/COleControl::ScrollWindow.md)  
  
-   [GetClientRect](../Topic/COleControl::GetClientRect.md)  
  
 Dans les contrôles sans fenêtre, vous devez toujours utiliser les fonctions membres de `COleControl` au lieu des fonctions membres correspondantes de `CWnd` ou de leurs fonctions connexes API Win32.  
  
 Vous pouvez souhaiter qu'un contrôle sans fenêtre soit la cible d'une opération de glisser\-déplacer OLE.  Normalement, cela suppose que la fenêtre de contrôle est stockée en tant que cible de suppression.  Puisque le contrôle n'a aucune fenêtre qui lui est propre, le conteneur utilise sa propre fenêtre comme cible de suppression.  Le contrôle fournit une implémentation de l'interface de `IDropTarget` à laquelle le conteneur peut déléguer des appels au moment opportun.  Pour exposer cette interface au conteneur, substituer [COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md).  Par exemple :  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/CPP/providing-windowless-activation_4.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)