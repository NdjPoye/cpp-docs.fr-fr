---
title: "Utilisation d&#39;objets fen&#234;tres | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres enfants, utiliser"
  - "objets fenêtres, utiliser"
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Utilisation d&#39;objets fen&#234;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisation des appels windows pour deux types d'activité :  
  
-   Messages windows de gestion  
  
-   Dessiner dans la fenêtre  
  
 Pour traiter les messages windows dans n'importe quelle fenêtre, notamment sur vos propres fenêtres enfants, consultez l'[Mapper des messages aux fonctions](../mfc/reference/mapping-messages-to-functions.md) pour mapper les messages à votre classe windows C\+\+.  Entrez les fonctions membres responsables de messages dans la classe.  
  
 La plupart de dessin dans une application framework se produit dans la vue, dont la fonction membre d'[OnDraw](../Topic/CView::OnDraw.md) est appelée chaque fois que le contenu de la fenêtre doit être dessiné.  Si votre fenêtre est un enfant de la vue, vous pouvez déléguer partie de dessin de la vue dans votre fenêtre enfant en demandant à l'appel d'un `OnDraw` les fonctions membres de votre fenêtre.  
  
 Dans tous les cas, vous aurez besoin d'un contexte de périphérique pour ajouter.  Vous pouvez utiliser le stylet magasin, le pinceau, ainsi que d'autres objets graphiques contenus dans le contexte de périphérique associé à la fenêtre.  Vous pouvez modifier ces objets pour obtenir les effets de dessin dont vous avez besoin.  Votre contexte de périphérique installée comme vous ouvrira, appelez les fonctions membres de la classe [CDC](../mfc/reference/cdc-class.md) \(classe de périphérique et pour tracer des lignes, des formes, et le texte ; pour utiliser des couleurs ; et pour fonctionner avec un système de coordonnées.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)  
  
-   [Dessin dans un affichage](../mfc/drawing-in-a-view.md)  
  
-   [Contextes de périphérique](../mfc/device-contexts.md)  
  
-   [Objets graphiques](../mfc/graphic-objects.md)  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)