---
title: "Personnalisation de l&#39;apparence d&#39;un contr&#244;le ToolBar | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBSTYLE_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBar (classe), styles"
  - "CToolBarCtrl (classe), styles d'objets"
  - "barres d'outils plates"
  - "TBSTYLE_ (styles)"
  - "contrôles de barre d'outils (MFC), style"
  - "barres d'outils transparentes"
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation de l&#39;apparence d&#39;un contr&#244;le ToolBar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `CToolBarCtrl` fournit plusieurs styles qui influencent la présentation \(et, occasionnellement, le comportement\) de l'objet barre d'outils.  Modifiez l'objet barre d'outils en définissant le paramètre `dwCtrlStyle` de la fonction membre `CToolBarCtrl::Create` \(ou `CToolBar::CreateEx`\), lorsque vous créez le contrôle de la barre d'outils.  
  
 Les styles suivants affectent l'aspect « 3D » dess boutons des barres d'outils et le positionnement du texte du bouton :  
  
-   **TBSTYLE\_FLAT** crée une barre d'outils en deux dimensions où à la fois la barre d'outils et les boutons sont transparents.  Le texte du bouton apparaît sous l'image bitmap de bouton.  Lorsque le style est utilisée, le bouton sous le curseur est automatiquement mis en surbrillance.  
  
-   **TBSTYLE\_TRANSPARENT** crée une barre d'outils transparente.  Dans la barre d'outils transparente, la barre d'outils est transparente mais les boutons ne sont pas.  Le texte du bouton apparaît sous l'image bitmap de bouton.  
  
-   **TBSTYLE\_LIST** Place le texte du bouton à droite des bitmap de bouton.  
  
> [!NOTE]
>  Pour éviter des problèmes de dessin, les styles **TBSTYLE\_FLAT** et **TBSTYLE\_TRANSPARENT** doivent être définis avant que l'objet barre d'outils soit visible.  
  
 Les styles suivants déterminent si la barre d'outils permet à un utilisateur de repositionner des boutons individuels dans un objet barre d'outils à l'aide d'un glisser\-déplacer :  
  
-   **TBSTYLE\_ALTDRAG** permet aux utilisateurs de modifier la position d'un bouton de barre d'outils en le faisant glisser tout en maintenant la touche ALT.  Si ce style n'est spécifié, l'utilisateur doit contenir MAJ enfoncée tout en faisant glisser un bouton.  
  
    > [!NOTE]
    >  Le style `CCS_ADJUSTABLE` doit être spécifié pour permettre aux boutons des barres d'outils d'être glissés.  
  
-   **TBSTYLE\_REGISTERDROP** génère des messages de notification **TBN\_GETOBJECT** pour demander des objets de suppression de cible lorsque le pointeur de la souris passe sur les boutons de la barre d'outils.  
  
 Les styles restants affectent les aspects visuels et non visuels de l'objet barre d'outils :  
  
-   `TBSTYLE_WRAPABLE` crée une barre d'outils qui peut avoir plusieurs lignes de boutons.  Les boutons de la barre d'outils peuvent "encapsuler" à la ligne suivante lorsque la barre d'outils est trop étroite pour inclure tous les boutons sur la même ligne.  L'habillage se produit sur les limites non group et de séparation.  
  
-   **TBSTYLE\_CUSTOMERASE** génère des messages de notification de **NM\_CUSTOMDRAW** lorsqu'il traite les messages `WM_ERASEBKGND`.  
  
-   `TBSTYLE_TOOLTIPS` crée un contrôle d'info\-bulle qu'une application peut utiliser pour afficher un texte descriptif pour les boutons de la barre d'outils.  
  
 Pour une liste complète des styles de la barre d'outils et les styles étendus, consultez [Contrôle de la barre d'outils et styles les boutons](http://msdn.microsoft.com/library/windows/desktop/bb760439) et [Styles étendus de la barre d'outils](http://msdn.microsoft.com/library/windows/desktop/bb760430) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)