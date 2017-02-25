---
title: "CToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl class"
  - "data tips [C++]"
  - "info-bulles (C++), tool tip controls"
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule les fonctionnalités d'un contrôle d'info\-bulle « , » une petite fenêtre indépendante qui affiche une ligne de texte unique qui décrit l'objectif d'un outil dans une application.  
  
## Syntaxe  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](../Topic/CToolTipCtrl::CToolTipCtrl.md)|Construit un objet `CToolTipCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CToolTipCtrl::Activate](../Topic/CToolTipCtrl::Activate.md)|Active et place le contrôle d'info\-bulle.|  
|[CToolTipCtrl::AddTool](../Topic/CToolTipCtrl::AddTool.md)|Enregistre un outil avec le contrôle d'info\-bulle.|  
|[CToolTipCtrl::AdjustRect](../Topic/CToolTipCtrl::AdjustRect.md)|Convertit entre le rectangle d'affichage du texte d'un contrôle d'info\-bulle et son rectangle de fenêtre.|  
|[CToolTipCtrl::Create](../Topic/CToolTipCtrl::Create.md)|Crée un contrôle d'info\-bulle et l'attache à un objet d' `CToolTipCtrl` .|  
|[CToolTipCtrl::CreateEx](../Topic/CToolTipCtrl::CreateEx.md)|Crée un contrôle d'info\-bulle avec les styles étendus par windows spécifiées et l'attache à un objet d' `CToolTipCtrl` .|  
|[CToolTipCtrl::DelTool](../Topic/CToolTipCtrl::DelTool.md)|Supprime un outil du contrôle d'info\-bulle.|  
|[CToolTipCtrl::GetBubbleSize](../Topic/CToolTipCtrl::GetBubbleSize.md)|Extrait la taille de l'info\-bulle.|  
|[CToolTipCtrl::GetCurrentTool](../Topic/CToolTipCtrl::GetCurrentTool.md)|Récupère des informations, telles que la taille, la position, et le texte, de la fenêtre d'info\-bulle que le contrôle d'info\-bulle actuellement affiche.|  
|[CToolTipCtrl::GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md)|Extrait l'initial, le menu contextuel, et les durées de reshow qui sont actuellement définies pour un contrôle d'info\-bulle.|  
|[CToolTipCtrl::GetMargin](../Topic/CToolTipCtrl::GetMargin.md)|Récupère le supérieur, gauche, base, et droite les marges définies pour une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md)|Extrait la largeur maximale pour une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::GetText](../Topic/CToolTipCtrl::GetText.md)|Extrait le texte qu'un contrôle d'info\-bulle met à jour pour un outil.|  
|[CToolTipCtrl::GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md)|Extrait la couleur d'arrière\-plan dans une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md)|Extrait la couleur du texte dans une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::GetTitle](../Topic/CToolTipCtrl::GetTitle.md)|Récupère le titre du contrôle d'info\-bulle actuellement.|  
|[CToolTipCtrl::GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md)|Récupère un nombre des outils mis à jour par un contrôle d'info\-bulle.|  
|[CToolTipCtrl::GetToolInfo](../Topic/CToolTipCtrl::GetToolInfo.md)|Récupère les informations qu'un contrôle d'info\-bulle met à jour sur un outil.|  
|[CToolTipCtrl::HitTest](../Topic/CToolTipCtrl::HitTest.md)|Teste un point pour déterminer s'il est dans le rectangle englobant de l'outil donné.  Si oui, récupère des informations sur l'outil.|  
|[CToolTipCtrl::Pop](../Topic/CToolTipCtrl::Pop.md)|Supprime une fenêtre d'info\-bulle affichée dans la vue.|  
|[CToolTipCtrl::Popup](../Topic/CToolTipCtrl::Popup.md)|Pour afficher le contrôle d'info\-bulle actuellement aux coordonnées du dernier message de la souris.|  
|[CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md)|Passe un message de la souris sur un contrôle d'info\-bulle pour traiter.|  
|[CToolTipCtrl::SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md)|Définit l'initial, le menu contextuel, et les durées de reshow pour un contrôle d'info\-bulle.|  
|[CToolTipCtrl::SetMargin](../Topic/CToolTipCtrl::SetMargin.md)|Définit le niveau supérieur, gauche, base, et droite des marges pour une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md)|Définit la largeur maximale pour une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md)|Définit la couleur d'arrière\-plan dans une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md)|Définit la couleur du texte dans une fenêtre d'info\-bulle.|  
|[CToolTipCtrl::SetTitle](../Topic/CToolTipCtrl::SetTitle.md)|Ajoute une chaîne standard d'icône et de titre à une info\-bulle.|  
|[CToolTipCtrl::SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md)|Définit les informations qu'une info\-bulle met à jour pour un outil.|  
|[CToolTipCtrl::SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md)|Définit un nouveau rectangle englobant d'un outil.|  
|[CToolTipCtrl::SetWindowTheme](../Topic/CToolTipCtrl::SetWindowTheme.md)|Définit le style de la fenêtre d'info\-bulle.|  
|[CToolTipCtrl::Update](../Topic/CToolTipCtrl::Update.md)|Force l'outil actuel à redessiner.|  
|[CToolTipCtrl::UpdateTipText](../Topic/CToolTipCtrl::UpdateTipText.md)|Définit le texte d'info\-bulle pour un outil.|  
  
## Notes  
 Un « outil » est une fenêtre, telle qu'une fenêtre enfant ou un contrôle, ou une zone rectangulaire définie par l'application dans une zone cliente de la fenêtre.  Une info\-bulle est masquée le plus souvent, apparaissant uniquement lorsque l'utilisateur place le curseur sur un outil et des feuilles il existe d'environ un moitié seconde.  L'info\-bulle apparaît près de le curseur et disparaît lorsque l'utilisateur clique sur un bouton de souris ou ferme le curseur l'outil.  
  
 `CToolTipCtrl` fournit les fonctionnalités pour contrôler la durée de démarrage et durée de l'info\-bulle, les largeurs de marge entourant le texte d'info\-bulle, de la largeur de la fenêtre d'info\-bulle elle\-même, et la couleur du texte et de l'arrière\-plan de l'info\-bulle.  Un seul contrôle d'info\-bulle peut fournir des informations pour plusieurs outil.  
  
 La classe d' `CToolTipCtrl` fournit les fonctionnalités du contrôle commun tooltip windows.  Ce contrôle \(et par conséquent la classe d' `CToolTipCtrl` \) est disponible uniquement aux programmes s'exécutant sous les versions de Windows 3,51 95\/98 et Windows NT et versions ultérieures.  
  
 Pour plus d'informations sur l'activation des info\-bulles, consultez l' [Info\-bulles dans les fenêtres non dérivées de CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).  
  
 Pour plus d'informations sur l'utilisation `CToolTipCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CToolTipCtrl](../../mfc/using-ctooltipctrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)