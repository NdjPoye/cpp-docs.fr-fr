---
title: "Construction d&#39;objets en une et en deux &#233;tapes | Microsoft Docs"
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
  - "création d'objet, objets graphiques"
  - "objets (C++), créer des objets graphiques"
  - "objets (C++), objets graphiques"
  - "construction d'objets en une et en deux étapes"
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Construction d&#39;objets en une et en deux &#233;tapes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous avez le choix entre deux techniques permettant de créer des objets graphiques, tels que les stylets et les pinceaux :  
  
-   *Construction d'une étape*: Construire et initialisez l'objet dans une étape, toutes avec le constructeur.  
  
-   *Construction à deux niveaux*: Construire et initialisez l'objet à deux étapes séparées.  Le constructeur crée l'objet et une fonction d'initialisation l'initialise.  
  
 La construction à deux niveaux est toujours plus sécurisée.  Dans la construction d'une étape, le constructeur peut lever une exception si vous fournissez les arguments incorrects ou l'allocation de mémoire échoue.  Ce problème est évité par la construction à deux niveaux, même si vous devez vérifier l'échec.  Dans l'un et l'autre cas, la destruction de l'objet est identique.  
  
> [!NOTE]
>  Ces techniques s'appliquent à créer tous les objets, et pas simplement objets graphiques.  
  
## Exemple de deux techniques de construction  
 Un bref exemple suivant illustre les deux méthodes de construction d'un objet de stylet :  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/CPP/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Objets graphiques](../mfc/graphic-objects.md)  
  
-   [Sélection d'un objet graphique dans un contexte de périphérique](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Contextes de périphérique](../mfc/device-contexts.md)  
  
-   [Dessin dans une vue](../mfc/drawing-in-a-view.md)  
  
## Voir aussi  
 [Objets graphiques](../mfc/graphic-objects.md)