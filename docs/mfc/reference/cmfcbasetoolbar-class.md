---
title: "CMFCBaseToolBar Class | Microsoft Docs"
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
  - "CMFCBaseToolBar::CreateObject"
  - "~CMFCBaseToolBar"
  - "CMFCBaseToolBar"
  - "CMFCBaseToolBar::CMFCBaseToolBar"
  - "CMFCBaseToolBar::~CMFCBaseToolBar"
  - "CMFCBaseToolBar.~CMFCBaseToolBar"
  - "CreateObject"
  - "CMFCBaseToolBar.CMFCBaseToolBar"
  - "CMFCBaseToolBar.CreateObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseToolBar destructor"
  - "CMFCBaseToolBar class"
  - "CMFCBaseToolBar class, constructeur"
  - "CMFCBaseToolBar class, destructeur"
  - "CreateObject method"
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCBaseToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe de base pour les barres d'outils.  
  
## Syntaxe  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|Constructeur par défaut.|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCBaseToolBar::GetDockingMode](../Topic/CMFCBaseToolBar::GetDockingMode.md)|Retourne le mode d'ancrage.  \(Substitutions [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md).\)|  
|[CMFCBaseToolBar::GetMinSize](../Topic/CMFCBaseToolBar::GetMinSize.md)|Retourne la taille minimale d'une barre d'outils.  \(Substitutions [CPane::GetMinSize](../Topic/CPane::GetMinSize.md).\)|  
|[CMFCBaseToolBar::OnAfterChangeParent](../Topic/CMFCBaseToolBar::OnAfterChangeParent.md)|Appelé par l'infrastructure après le parent du volet change.  \(Substitutions [CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md).\)|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## Configuration requise  
 **en\-tête :** afxbasetoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)