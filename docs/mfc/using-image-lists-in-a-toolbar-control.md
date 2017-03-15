---
title: "Utilisation de listes d&#39;images dans un contr&#244;le ToolBar | Microsoft Docs"
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
  - "CToolBarCtrl (classe), listes d'images"
  - "listes d'images (C++), contrôles de barre d'outils"
  - "contrôles de barre d'outils (MFC), image"
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation de listes d&#39;images dans un contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, les images utilisées par les boutons dans un contrôle de la barre d'outils sont stockées sous forme de bitmap unique.  Toutefois, vous pouvez également enregistrer les images des boutons dans un ensemble de listes d'image.  L'objet de contrôle de la barre d'outils peut utiliser jusqu'à trois listes d'images distinctes :  
  
-   La liste des images active contient des images des boutons de la barre d'outils qui sont actuellement activées.  
  
-   La liste des images inactive contient des images des boutons de la barre d'outils qui sont actuellement désactivées.  
  
-   La liste des images en surbrillance contient des images des boutons de la barre d'outils qui sont actuellement mises en surbrillance.  Cette liste des images est utilisée uniquement lorsque la barre d'outils utilise le style **TBSTYLE\_FLAT**.  
  
 Ces listes d'images sont utilisées par le contrôle de la barre d'outils lorsque vous les associez à l'objet `CToolBarCtrl`.  Cette association est effectuée en effectuant des appels à [CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md), à [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md), et [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md).  
  
 Par défaut, MFC utilise la classe `CToolBar` pour implémenter des barres d'outils d'application MFC.  Toutefois, la fonction membre `GetToolBarCtrl` peut être utilisée pour récupérer l'objet incorporé `CToolBarCtrl`.  Vous pouvez ensuite faire des appels aux fonctions membres `CToolBarCtrl` utilisant l'objet retourné.  
  
 L'exemple suivant illustre cette technique en affectant une liste des images active \(`m_ToolBarImages`\) ou désactives \(`m_ToolBarDisabledImages`\)à un objet de `CToolBarCtrl` \(`m_ToolBarCtrl`\).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/CPP/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  Les listes d'images utilisées par l'objet barre d'outils doivent être des objets permanents.  Par conséquent, elles sont généralement des membres de données d'une classe de MFC ; dans cet exemple, la classe cadre de fenêtre principale.  
  
 Une fois que les listes d'images sont associées à l'objet `CToolBarCtrl`, l'environnement affiche automatiquement l'image de bouton appropriée.  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)