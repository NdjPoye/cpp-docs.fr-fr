---
title: "CControlBar Class | Microsoft Docs"
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
  - "CControlBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar class"
  - "control bars [C++], classe de base"
  - "dialog bars, classe de base"
  - "OLE resize bars"
  - "OLE resize bars, classe de base"
  - "barres d'état, classe de base"
  - "barres d'outils (C++), classe de base"
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CControlBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base des classes de barres de contrôle [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), et [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## Syntaxe  
  
```  
class CControlBar : public CWnd  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CControlBar::CControlBar](../Topic/CControlBar::CControlBar.md)|Construit un objet `CControlBar`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CControlBar::CalcDynamicLayout](../Topic/CControlBar::CalcDynamicLayout.md)|Retourne la taille d'une barre de contrôle dynamique comme un objet [CSize](../../atl-mfc-shared/reference/csize-class.md).|  
|[CControlBar::CalcFixedLayout](../Topic/CControlBar::CalcFixedLayout.md)|Retourne la taille de la barre de contrôle comme objet de [CSize](../../atl-mfc-shared/reference/csize-class.md).|  
|[CControlBar::CalcInsideRect](../Topic/CControlBar::CalcInsideRect.md)|Retourne les dimensions actuelles de la zone de barre de contrôles ; notamment les bordures.|  
|[CControlBar::DoPaint](../Topic/CControlBar::DoPaint.md)|Affiche les bordures et la pince de la barre de contrôles.|  
|[CControlBar::DrawBorders](../Topic/CControlBar::DrawBorders.md)|Affiche les bordures de la barre de contrôles.|  
|[CControlBar::DrawGripper](../Topic/CControlBar::DrawGripper.md)|Affiche les bordures de la barre de contrôles.|  
|[CControlBar::EnableDocking](../Topic/CControlBar::EnableDocking.md)|Permet d'ancrer ou de détacher une barre de contrôle.|  
|[CControlBar::GetBarStyle](../Topic/CControlBar::GetBarStyle.md)|Récupère les paramètres de style de barres de contrôles.|  
|[CControlBar::GetBorders](../Topic/CControlBar::GetBorders.md)|Récupère les valeurs de bordure de la barre de contrôles.|  
|[CControlBar::GetCount](../Topic/CControlBar::GetCount.md)|Retourne le nombre d'éléments non\-`HWND` dans la barre de contrôle.|  
|[CControlBar::GetDockingFrame](../Topic/CControlBar::GetDockingFrame.md)|Retourne un pointeur vers le frame sur lequel une barre de contrôle est ancrée.|  
|[CControlBar::IsFloating](../Topic/CControlBar::IsFloating.md)|Retourne une valeur différente de zéro si la barre de contrôles en question est une barre de contrôle flottante.|  
|[CControlBar::OnUpdateCmdUI](../Topic/CControlBar::OnUpdateCmdUI.md)|Appelle les gestionnaires de la commande interface utilisateur.|  
|[CControlBar::SetBarStyle](../Topic/CControlBar::SetBarStyle.md)|Modifie les paramètres de style de barres de contrôle.|  
|[CControlBar::SetBorders](../Topic/CControlBar::SetBorders.md)|Définit les valeurs de bordure de la barre de contrôle.|  
|[CControlBar::SetInPlaceOwner](../Topic/CControlBar::SetInPlaceOwner.md)|Modifie le propriétaire sur place d'une barre de contrôle.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CControlBar::m\_bAutoDelete](../Topic/CControlBar::m_bAutoDelete.md)|Si une valeur est différente de zéro, l'objet `CControlBar` est supprimé lorsque la barre de contrôles Windows est détruite.|  
|[CControlBar::m\_pInPlaceOwner](../Topic/CControlBar::m_pInPlaceOwner.md)|Le propriétaire sur place de la barre de contrôles.|  
  
## Notes  
 Une barre de contrôles est une fenêtre qui est généralement alignée à gauche ou à droite d'une fenêtre frame.  Elle peut contenir des éléments enfants qui sont soit de contrôles basés sur `HWND`, qui sont des fenêtres qui génèrent et répondent aux messages Windows, ou des éléments non basés sur `HWND`, qui ne sont pas des fenêtres et sont gérés par le code d'application ou le code d'infrastructure.  Les zones de liste et les contrôles d'édition sont des exemples de contrôles basés sur `HWND`; les volets et les boutons bitmap de barre d'état sont des exemples de contrôles non\-basés sur `HWND`.  
  
 Les fenêtres de barre de contrôle sont généralement des fenêtres enfant d'une fenêtre frame parente et sont généralement les frères de l'affichage client ou le client MDI de la fenêtre frame.  Un objet `CControlBar` utilise des informations sur le rectangle client de la fenêtre parente pour se positionner.  Il signale à la fenêtre parente la quantité d'espace qui reste non alloué dans la zone cliente parente de la fenêtre.  
  
 Pour plus d'informations sur `CControlBar`, consultez:  
  
-   [Barres de contrôles](../../mfc/control-bars.md)  
  
-   [Note technique 31 : Barres de contrôles](../../mfc/tn031-control-bars.md).  
  
-   L'article de la Base de connaissances Q242577 : PRB : Les gestionnaires d'interface utilisateur de commande de mise à jour ne fonctionnent pas avec le menu joint à une boîte de dialogue  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## Configuration requise  
 **En\-tête:** afxext.h  
  
## Voir aussi  
 [Exemple MFC CTRLBARS](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBar Class](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar Class](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)   
 [CReBar Class](../../mfc/reference/crebar-class.md)