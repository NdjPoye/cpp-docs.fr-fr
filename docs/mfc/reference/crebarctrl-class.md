---
title: "CReBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBarCtrl class"
  - "rebar controls, control bar"
  - "rebar controls, CReBarCtrl class"
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CReBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctionnalités d'un contrôle rebar, qui est un conteneur pour une fenêtre enfant.  
  
## Syntaxe  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CReBarCtrl::CReBarCtrl](../Topic/CReBarCtrl::CReBarCtrl.md)|Construit un objet `CReBarCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CReBarCtrl::BeginDrag](../Topic/CReBarCtrl::BeginDrag.md)|Définit le contrôle rebar en mode glisser\-déplacer.|  
|[CReBarCtrl::Create](../Topic/CReBarCtrl::Create.md)|Crée le contrôle rebar et l'attache à l'objet d' `CReBarCtrl` .|  
|[CReBarCtrl::CreateEx](../Topic/CReBarCtrl::CreateEx.md)|Crée un contrôle rebar avec les styles étendus par windows spécifiées et l'attache à un objet d' `CReBarCtrl` .|  
|[CReBarCtrl::DeleteBand](../Topic/CReBarCtrl::DeleteBand.md)|Supprime une bande d'un contrôle rebar.|  
|[CReBarCtrl::DragMove](../Topic/CReBarCtrl::DragMove.md)|Met à jour la position de glisser\-déplacer dans le contrôle rebar après un appel à `BeginDrag`.|  
|[CReBarCtrl::EndDrag](../Topic/CReBarCtrl::EndDrag.md)|Termine l'opération de glisser\-déplacer rebar du contrôle.|  
|[CReBarCtrl::GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md)|Récupère les zones d'une bande.|  
|[CReBarCtrl::GetBandCount](../Topic/CReBarCtrl::GetBandCount.md)|Récupère le nombre de bandes actuel dans le contrôle rebar.|  
|[CReBarCtrl::GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md)|Récupère des informations sur une bande spécifiée dans un contrôle rebar.|  
|[CReBarCtrl::GetBandMargins](../Topic/CReBarCtrl::GetBandMargins.md)|Récupère les marges d'une bande.|  
|[CReBarCtrl::GetBarHeight](../Topic/CReBarCtrl::GetBarHeight.md)|Extrait la hauteur du contrôle rebar.|  
|[CReBarCtrl::GetBarInfo](../Topic/CReBarCtrl::GetBarInfo.md)|Récupère des informations sur le contrôle rebar et la liste d'images qu'elle utilise.|  
|[CReBarCtrl::GetBkColor](../Topic/CReBarCtrl::GetBkColor.md)|Extrait la couleur d'arrière\-plan par défaut d'un contrôle rebar.|  
|[CReBarCtrl::GetColorScheme](../Topic/CReBarCtrl::GetColorScheme.md)|Extrait la structure de [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) associée au contrôle rebar.|  
|[CReBarCtrl::GetDropTarget](../Topic/CReBarCtrl::GetDropTarget.md)|Récupère le pointeur d'interface rebar d' `IDropTarget` d'un contrôle.|  
|[CReBarCtrl::GetExtendedStyle](../Topic/CReBarCtrl::GetExtendedStyle.md)|Obtient le style étendu du contrôle rebar actuel.|  
|[CReBarCtrl::GetImageList](../Topic/CReBarCtrl::GetImageList.md)|Récupère la liste d'images associée à un contrôle rebar.|  
|[CReBarCtrl::GetPalette](../Topic/CReBarCtrl::GetPalette.md)|Extrait la palette actuelle du contrôle rebar.|  
|[CReBarCtrl::GetRect](../Topic/CReBarCtrl::GetRect.md)|Récupère le rectangle englobant d'une bande données dans un contrôle rebar.|  
|[CReBarCtrl::GetRowCount](../Topic/CReBarCtrl::GetRowCount.md)|Récupère le nombre de lignes de bandes dans un contrôle rebar.|  
|[CReBarCtrl::GetRowHeight](../Topic/CReBarCtrl::GetRowHeight.md)|Extrait la hauteur d'une ligne spécifiée dans un contrôle rebar.|  
|[CReBarCtrl::GetTextColor](../Topic/CReBarCtrl::GetTextColor.md)|Extrait la couleur de texte par défaut rebar d'un contrôle.|  
|[CReBarCtrl::GetToolTips](../Topic/CReBarCtrl::GetToolTips.md)|Récupère le handle à tous les contrôles d'info\-bulle associé au contrôle rebar.|  
|[CReBarCtrl::HitTest](../Topic/CReBarCtrl::HitTest.md)|Détermine que la partie d'une bande rebar est à un point donné sur l'écran, si une bande rebar existe à ce stade.|  
|[CReBarCtrl::IDToIndex](../Topic/CReBarCtrl::IDToIndex.md)|Convertit un identificateur \(ID\) de bande à un index de bandes dans un contrôle rebar.|  
|[CReBarCtrl::InsertBand](../Topic/CReBarCtrl::InsertBand.md)|Insère une nouvelle bande dans un contrôle rebar.|  
|[CReBarCtrl::MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md)|Redimensionne une bande dans un contrôle rebar à sa taille la plus grande taille.|  
|[CReBarCtrl::MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md)|Redimensionne une bande dans un contrôle rebar à son petite taille.|  
|[CReBarCtrl::MoveBand](../Topic/CReBarCtrl::MoveBand.md)|Déplace une bande d'un index à un autre.|  
|[CReBarCtrl::PushChevron](../Topic/CReBarCtrl::PushChevron.md)|Pousse par programme un chevron.|  
|[CReBarCtrl::RestoreBand](../Topic/CReBarCtrl::RestoreBand.md)|Redimensionne une bande dans un contrôle rebar à sa taille idéale.|  
|[CReBarCtrl::SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md)|Définit les caractéristiques d'une bande existante dans un contrôle rebar.|  
|[CReBarCtrl::SetBandWidth](../Topic/CReBarCtrl::SetBandWidth.md)|Définit la largeur de la bande ancrée spécifiée dans le contrôle rebar actuel.|  
|[CReBarCtrl::SetBarInfo](../Topic/CReBarCtrl::SetBarInfo.md)|Définit les caractéristiques d'un contrôle rebar.|  
|[CReBarCtrl::SetBkColor](../Topic/CReBarCtrl::SetBkColor.md)|Définit la couleur d'arrière\-plan par défaut d'un contrôle rebar.|  
|[CReBarCtrl::SetColorScheme](../Topic/CReBarCtrl::SetColorScheme.md)|Définit le modèle de couleurs pour les boutons sur un contrôle rebar.|  
|[CReBarCtrl::SetExtendedStyle](../Topic/CReBarCtrl::SetExtendedStyle.md)|Définit les styles étendus pour le contrôle rebar actuel.|  
|[CReBarCtrl::SetImageList](../Topic/CReBarCtrl::SetImageList.md)|Définit la liste d'images rebar d'un contrôle.|  
|[CReBarCtrl::SetOwner](../Topic/CReBarCtrl::SetOwner.md)|Définit la fenêtre propriétaire rebar d'un contrôle.|  
|[CReBarCtrl::SetPalette](../Topic/CReBarCtrl::SetPalette.md)|Définit la palette actuelle du contrôle rebar.|  
|[CReBarCtrl::SetTextColor](../Topic/CReBarCtrl::SetTextColor.md)|Définit la couleur de texte par défaut rebar d'un contrôle.|  
|[CReBarCtrl::SetToolTips](../Topic/CReBarCtrl::SetToolTips.md)|Associe un contrôle d'info\-bulle avec le contrôle rebar.|  
|[CReBarCtrl::SetWindowTheme](../Topic/CReBarCtrl::SetWindowTheme.md)|Définit le style visuel du contrôle rebar.|  
|[CReBarCtrl::ShowBand](../Topic/CReBarCtrl::ShowBand.md)|Affiche ou masque une bande données dans un contrôle rebar.|  
|[CReBarCtrl::SizeToRect](../Topic/CReBarCtrl::SizeToRect.md)|Ajuste un contrôle rebar à un rectangle spécifié.|  
  
## Notes  
 L'application dans laquelle le contrôle rebar réside assigne la fenêtre enfant contenue par le contrôle rebar bande rebar.  La fenêtre enfant est généralement un autre contrôle commun.  
  
 Rebar les contrôles contiennent un ou plusieurs des bagages.  Chaque bande peut contenir une combinaison d'une barre de pinces, d'une bitmap, d'une étiquette de texte, et d'une fenêtre enfant.  La bande peut contenir qu'un seul de ces éléments.  
  
 Le contrôle rebar peut afficher la fenêtre enfant sur une bitmap spécifiée d'arrière\-plan.  Toutes les bandes rebar de contrôle peuvent être redimensionnées, sauf ceux qui utilisent le style de **RBBS\_FIXEDSIZE** .  Lorsque vous repositionnez ou redimensionnez une bande de contrôle rebar, le contrôle rebar gère la taille et la position de la fenêtre enfant assignée à la bande.  Pour redimensionner ou modifier l'ordre des bandes dans le contrôle, puis faire glisser la barre de pinces d'une bande.  
  
 L'illustration suivante montre un contrôle rebar doté de trois bandes :  
  
-   La bande 0 contient un contrôle de barre d'outils en deux dimensions et transparent.  
  
-   La bande 1 contient les boutons déroulants standard et entièrement transparents.  
  
-   La bande 2 contient une zone de liste déroulante et quatre boutons standard.  
  
     ![Exemple du menu Rebar](../../mfc/reference/media/vc4scc1.png "vc4SCC1")  
  
## Contrôle rebar  
 Prise en charge de contrôles rebar :  
  
-   Listes d'images.  
  
-   Gestion des messages.  
  
-   Fonctionnalités personnalisées de dessin.  
  
-   Divers styles de contrôle en plus de les styles de fenêtre standard.  Pour obtenir la liste de ces styles, consultez [Rebar styles de contrôle](http://msdn.microsoft.com/library/windows/desktop/bb774377) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations, consultez l' [Utilisation CReBarCtrl](../../mfc/using-crebarctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)