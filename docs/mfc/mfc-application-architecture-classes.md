---
title: "Classes d&#39;architecture des applications MFC | Microsoft Docs"
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
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes d'architecture des applications"
  - "classes (C++), MFC"
  - "MFC (C++), développement de l'application"
  - "MFC (C++), classes"
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes d&#39;architecture des applications MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes de cette catégorie fournissent à l'architecture d'une application framework.  Ils fournissent le courantes de fonctionnalités à la plupart des applications.  Vous remplissez le framework pour ajouter des fonctionnalités spécifiques à l'application.  En général, cela se fait en faisant dériver de nouvelles classes des classes de l'architecture, puis en ajoutant de nouveaux membres ou en remplaçant les fonctions membres existants.  
  
 [Assistant d'application](../mfc/reference/mfc-application-wizard.md) génèrent plusieurs types d'applications, qui utilisent l'infrastructure d'application des façons différentes.  Les applications de SDI \(interface monodocument\) et MDI \(interface\) MD utiliser pleinement partie de l'infrastructure appelée architecture documents\/Vue.  D'autres types d'applications, telles que les applications basées sur les boîtes de dialogue, formulaire\- basée sur des applications, et les DLL, utilisez uniquement certaines des fonctionnalités d'architecture documents\/Vue.  
  
 Les applications de documents\/vue contiennent un ou plusieurs jeux de documents, de vues, puis fenêtres cadres.  Objet modèle de document associe les classes pour chaque document\/vue\/ensemble du cadre.  
  
 Bien que vous ne devez pas utiliser l'architecture documents\/Vue dans votre application de MFC, il existe de nombreuses avantages à le faire.  La prise en charge du conteneur et de serveur OLE MFC est basée sur l'architecture documents\/Vue, comme prise en charge d'impression et d'aperçu avant impression.  
  
 Toutes les applications de MFC ont au moins deux objets : objet d'application dérivé de [CWinApp](../mfc/reference/cwinapp-class.md), et plusieurs tri de l'objet window principal, dérivé \(souvent indirectement\) de [CWnd](../mfc/reference/cwnd-class.md). \(Le plus souvent, la fenêtre principale est dérivée de [CFrameWnd](../mfc/reference/cframewnd-class.md), de[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), ou de [CDialog](../mfc/reference/cdialog-class.md), dérivés de `CWnd`.\)  
  
 Les applications qui utilisent l'architecture documents\/Vue contiennent des objets supplémentaires.  Les objets principaux sont :  
  
-   Objet d'application dérivé de la classe [CWinApp](../mfc/reference/cwinapp-class.md), comme indiqué précédemment.  
  
-   Un ou plusieurs objets de classe de document dérivés de la classe [CDocument](../mfc/reference/cdocument-class.md).  Les objets de classe de document sont responsables de la représentation interne des données manipulées dans la vue.  Ils peuvent être associés à un fichier de données.  
  
-   Un ou plusieurs objets de vue dérivés de la classe [CView](../mfc/reference/cview-class.md).  Chaque vue est une fenêtre qui est associée à un élément et associée à une fenêtre cadre.  Les vues affichent et manipulent les données contenues dans un objet de classe de document.  
  
 Les applications de documents\/vue contiennent également des fenêtres cadres \(dérivées d'[CFrameWnd](../mfc/reference/cframewnd-class.md)\) et des modèles de document \(dérivés d'[CDocTemplate](../mfc/reference/cdoctemplate-class.md)\).  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)