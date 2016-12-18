---
title: "Cr&#233;ation de fen&#234;tres frame de document | Microsoft Docs"
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
  - "fenêtres frame de document, créer"
  - "modèles de document, et fenêtres frame de document"
  - "fenêtres frame (C++), créer"
  - "MFC (C++), fenêtres frame"
  - "Runtime (classe), et création de fenêtre frame de document"
  - "runtime, informations de classe"
  - "fenêtres (C++), créer"
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation de fen&#234;tres frame de document
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Création de Document\/Vue](../mfc/document-view-creation.md) montre comment l'objet [CDocTemplate](../mfc/reference/cdoctemplate-class.md) orchestre la création de la fenêtre de cadre, du document, et de la vue et les connecter tous ensemble.  Trois arguments [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) au constructeur `CDocTemplate` spécifient la fenêtre de cadre, le document, et les classes d'affichage que le modèle de document crée dynamiquement en réponse aux commandes de l'utilisateur telles que la nouvelle commande du menu Fichier ou la commande de nouvelle fenêtre dans un menu Fenêtre MDI.  Le modèle de document stocke ces informations pour une utilisation ultérieure lorsqu'il crée une fenêtre cadre d'une vue et d'un document.  
  
 Pour que le mécanisme de [RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md) fonctionne correctement, vos classes de fenêtre cadre dérivées doivent être déclarées avec la macro [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md).  Cela est dû au fait que l'infrastructure doit créer d'autres cadres de document à l'aide du mécanisme de gestion de construction de la classe `CObject`.  
  
 Lorsque l'utilisateur sélectionne une commande qui crée un document, l'infrastructure demande au modèle de document de créer l'objet document, sa vue, et la fenêtre cadre qui affiche la vue.  Lorsqu'il crée la fenêtre cadre de document, le modèle de document crée un objet de la classe appropriée — une classe dérivée de [CFrameWnd](../mfc/reference/cframewnd-class.md) pour une application SDI ou de [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) pour une application MDI.  L'infrastructure appelle la méthode cadre de fenêtre [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) de l'objet pour obtenir les informations de création de ressources et créer la fenêtre Windows.  L'infrastructure joint le handle de fenêtre à l'objet cadre de fenêtre.  Il crée alors la vue dans une fenêtre enfant de la fenêtre cadre de document.  
  
 Soyez prudent lorsque vous décider [à quel moment initialiser](../mfc/when-to-initialize-cwnd-objects.md) votre objet dérivé de `CWnd`.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [En faisant dériver une classe de CObject \(son mécanisme de création dynamique\)](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Création de documents\/vue \(création de modèles et de fenêtre cadre\)](../mfc/document-view-creation.md)  
  
-   [Destruction des fenêtres de cadres](../mfc/destroying-frame-windows.md)  
  
## Voir aussi  
 [Utilisation de fenêtres frame](../mfc/using-frame-windows.md)