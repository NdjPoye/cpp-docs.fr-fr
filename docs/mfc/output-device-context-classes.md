---
title: "Classes de sortie (contexte de p&#233;riph&#233;rique) | Microsoft Docs"
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
  - "vc.classes.output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contextes de périphérique, classes"
  - "classes de sortie"
  - "classes de peinture"
  - "classes d'impression"
  - "classes de sortie écran"
  - "classes de dessin de fenêtre"
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de sortie (contexte de p&#233;riph&#233;rique)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes encapsulent les différents types de contextes de périphérique disponibles dans windows.  
  
 La plupart des classes suivantes encapsulent un handle à un contexte de périphérique Windows.  Un contexte de périphérique est un objet Windows qui contient des informations sur les attributs de dessin d'un périphérique tels qu'une vue ou une imprimante.  Tous les appels de dessin sont effectués via un objet contexte de périphérique.  Les classes supplémentaires dérivées de `CDC` encapsulent des fonctionnalités spéciales de contexte de périphérique, y compris la prise en charge des métafichiers Windows.  
  
 [CDC](../mfc/reference/cdc-class.md)  
 La classe de base pour les contextes de périphérique.  Utilisé pour accéder directement à la vue entière et pour accéder à des contextes sans affichage tels que des imprimantes.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 Un contexte d'affichage utilisé dans les méthodes Windows `OnPaint`.  Appelle automatiquement `BeginPaint` à la construction et `EndPaint` à la destruction.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Un contexte d'affichage des domaines client Windows.  Utilisé, par exemple, pour tracer en réponse immédiate aux événements de la souris.  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 Un contexte d'affichage de fenêtres entières, qui inclut les zones client et non client.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Un contexte de périphérique pour les métafichiers Windows.  Un métafichier Windows contient une séquence de commandes GDI \(Graphics Device Interface\) qui peuvent être relues pour créer une image.  Les appels effectués aux méthodes `CMetaFileDC` sont stockés dans un métafichier.  
  
## Classes liées  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Contient des paires \(x, y\) de coordonnées.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Contient la distance, les positions relatives, ou les valeurs couplées.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Contient des coordonnées de zones rectangulaires.  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 Encapsule une région GDI pour manipuler une zone elliptique, polygonale ou irrégulière dans une fenêtre.  Utilisé conjointement avec les méthodes de réduction de la classe `CDC`.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Affiche et gère l'interface utilisateur pour redimensionner ou déplacer les objets rectangulaires.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Affiche une boîte de dialogue standard pour sélectionner une couleur.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Affiche une boîte de dialogue standard pour sélectionner une police.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Affiche une boîte de dialogue standard pour imprimer un fichier.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)