---
title: "S&#233;lection d&#39;un objet graphique dans un contexte de p&#233;riph&#233;rique | Microsoft Docs"
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
  - "contextes de périphérique, objets graphiques"
  - "contextes de périphérique, sélectionner des objets graphiques dans"
  - "objets GDI (C++), contextes de périphérique"
  - "objets graphiques, sélectionner dans le contexte de périphérique"
  - "durée de vie, objets graphiques"
  - "SelectObject (méthode)"
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;lection d&#39;un objet graphique dans un contexte de p&#233;riph&#233;rique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique à utiliser des objets graphiques dans le contexte du périphérique d'une fenêtre.  Après avoir [créer un objet de dessin](../mfc/one-stage-and-two-stage-construction-of-objects.md), vous devez sélectionner dans le contexte de périphérique à la place de l'objet par défaut stocké que :  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/CPP/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## Durée de vie des objets graphiques  
 L'objet graphique retourné par [SelectObject](../Topic/CDC::SelectObject.md) est "temporaire". Cela étant, il est supprimé par la fonction membre [OnIdle](../Topic/CWinApp::OnIdle.md) de la classe `CWinApp` la prochaine exécution du programme traverse une durée d'inactivité.  Tant que vous utilisez l'objet retourné par `SelectObject` dans une seule fonction sans restituer le contrôle à la boucle de message principal, vous n'aurez aucun problème.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Objets graphiques](../mfc/graphic-objects.md)  
  
-   [Construction d'objets graphiques en une et en deux étapes](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Contextes de périphérique](../mfc/device-contexts.md)  
  
-   [Dessin dans une vue](../mfc/drawing-in-a-view.md)  
  
## Voir aussi  
 [Objets graphiques](../mfc/graphic-objects.md)