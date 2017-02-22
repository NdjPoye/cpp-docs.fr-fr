---
title: "D&#233;river des contr&#244;les d&#39;un contr&#244;le standard | Microsoft Docs"
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
  - "contrôles communs (C++), dériver de"
  - "contrôles (MFC), dérivés"
  - "contrôles dérivés"
  - "contrôles standard"
  - "contrôles standard, dériver des contrôles de"
  - "contrôles Windows communs (C++), dériver de"
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# D&#233;river des contr&#244;les d&#39;un contr&#244;le standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme avec toute classe dérivée [CWnd](../mfc/reference/cwnd-class.md)\-, vous pouvez modifier le comportement de contrôle en faisant dériver une nouvelle classe d'une classe de contrôle existante.  
  
### Pour créer une classe de contrôle dérivée  
  
1.  Dérivez la classe d'une classe de contrôle existante et remplacez éventuellement la fonction membre **Créer** de sorte qu'elle fournisse les arguments nécessaires à la fonction **Créer** de la classe de base.  
  
2.  Fournit les fonctions membres responsables des messages et les entrées de la table des messages pour modifier le comportement du contrôle en réponse aux messages spécifiques Windows.  Consultez [Mappage de messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
3.  Fournissez les nouvelles fonctions membres pour étendre les fonctionnalités de contrôle \(facultatif\).  
  
 L'utilisation d'un contrôle dérivé dans une boîte de dialogue requiert un travail supplémentaire.  Les types et les positions des contrôles dans une boîte de dialogue sont normalement spécifiés dans une ressource modèle de la boîte de dialogue.  Si vous créez une classe de contrôle dérivée, vous ne pouvez pas le spécifier dans un modèle de la boîte de dialogue car le compilateur de ressources ne connaît rien de votre classe dérivée.  
  
#### Pour placer votre contrôle dérivé dans une boîte de dialogue  
  
1.  Incluez un objet de la classe de contrôle dérivée dans la déclaration de la classe de la boîte de dialogue dérivée.  
  
2.  Remplacer la fonction membre `OnInitDialog` dans la classe de la boîte de dialogue pour appeler la fonction membre `SubclassDlgItem` pour le contrôle dérivé.  
  
 `SubclassDlgItem` "sous\-classe dynamiquement" un contrôle créé depuis une boîte de dialogue.  Lorsqu'un contrôle est dynamiquement sous\-classé, situez\-vous dans Windows, traitez certains des messages dans votre propre application, puis transmettez les messages restants à Windows.  Pour plus d'informations, consultez la fonction membre de [DialogueFin](../Topic/CWnd::SubclassDlgItem.md) de la classe `CWnd` dans *le guide de MFC*.  L'exemple suivant montre comment vous pouvez entrer une substitution de `OnInitDialog` pour appeler `SubclassDlgItem`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/CPP/deriving-controls-from-a-standard-control_1.cpp)]  
  
 Le contrôle dérivé étant incorporé dans la classe de la boîte de dialogue, il est construit lorsque la boîte de dialogue est construite, et il est détruit lorsque la boîte de dialogue est détruite.  Comparez ce code à l'exemple de [Ajout des contrôles à la main](../mfc/adding-controls-by-hand.md).  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)