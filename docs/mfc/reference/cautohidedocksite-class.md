---
title: "CAutoHideDockSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAutoHideDockSite"
  - "AllowShowOnPaneMenu"
  - "CAutoHideDockSite::AllowShowOnPaneMenu"
  - "CAutoHideDockSite.AllowShowOnPaneMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AllowShowOnPaneMenu method"
  - "CAutoHideDockSite class"
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoHideDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAutoHideDockSite` étend [CDockSite Class](../../mfc/reference/cdocksite-class.md) à implémenter masquer automatiquement les volets d'ancrage.  
  
## Syntaxe  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CAutoHideDockSite::CAutoHideDockSite`|Construit un objet `CAutoHideDockSite`.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Indique si `CAutoHideDockSite` est affiché dans le menu de volet.|  
|[CAutoHideDockSite::CanAcceptPane](../Topic/CAutoHideDockSite::CanAcceptPane.md)|Détermine si un objet de base de volet est dérivé de [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](../Topic/CAutoHideDockSite::DockPane.md)|Ancre un volet à cet objet d' `CAuotHideDockSite` .|  
|[CAutoHideDockSite::GetAlignRect](../Topic/CAutoHideDockSite::GetAlignRect.md)|Extrait la taille du site d'ancrage en coordonnées d'écran.|  
|[CAutoHideDockSite::RepositionPanes](../Topic/CAutoHideDockSite::RepositionPanes.md)|Redessine le volet sur `CAutoHideDockSite` avec les marges et l'espacement totales du bouton.|  
|[CAutoHideDockSite::SetOffsetLeft](../Topic/CAutoHideDockSite::SetOffsetLeft.md)|Définit la marge située à gauche de la barre d'ancrage.|  
|[CAutoHideDockSite::SetOffsetRight](../Topic/CAutoHideDockSite::SetOffsetRight.md)|Définit la marge située à droite de la barre d'ancrage.|  
|[CAutoHideDockSite::UnSetAutoHideMode](../Topic/CAutoHideDockSite::UnSetAutoHideMode.md)|Appels [CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md) pour les objets sur `CAutoHideDockSite`.|  
  
### Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|[CAutoHideDockSite::m\_nExtraSpace](../Topic/CAutoHideDockSite::m_nExtraSpace.md)|Définit la taille de l'espace entre les barres d'outils et le bord de la barre d'ancrage.  Cet espace est mesuré du bord gauche ou du bord supérieur, selon l'alignement de l'espace d'ancrage.|  
  
## Notes  
 Lorsque vous appelez [CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md), l'infrastructure crée automatiquement un objet d' `CAutoHideDockSite` .  Dans la plupart des cas, vous ne devez pas devoir instancier ou utiliser cette classe directement.  
  
 La barre d'ancrage est l'intervalle entre le côté gauche du volet d'ancrage et le côté gauche de [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## Exemple  
 L'exemple suivant montre comment récupérer un objet d' `CAutoHideDockSite` d'un objet d' `CMFCAutoHideBar` , et comment définir les marges gauche et droite de la barre d'ancrage.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/CPP/cautohidedocksite-class_1.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxautohidedocksite.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)