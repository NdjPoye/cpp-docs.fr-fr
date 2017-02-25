---
title: "CMFCDropDownFrame Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDropDownFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownFrame class"
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMFCDropDownFrame Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit la fonctionnalité déroulante de la fenêtre frame aux barres d'outils déroulantes et des boutons de barre d'outils déroulants.  
  
## Syntaxe  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Constructeur par défaut.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDropDownFrame::Create](../Topic/CMFCDropDownFrame::Create.md)|Crée un objet `CMFCDropDownFrame`.|  
|`CMFCDropDownFrame::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCDropDownFrame::GetParentMenuBar](../Topic/CMFCDropDownFrame::GetParentMenuBar.md)|Extrait la barre de menus parent du frame déroulant.|  
|[CMFCDropDownFrame::GetParentPopupMenu](../Topic/CMFCDropDownFrame::GetParentPopupMenu.md)|Récupère le menu contextuel parent du frame déroulant.|  
|`CMFCDropDownFrame::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCDropDownFrame::RecalcLayout](../Topic/CMFCDropDownFrame::RecalcLayout.md)|Repositionne le frame déroulant.|  
|[CMFCDropDownFrame::SetAutoDestroy](../Topic/CMFCDropDownFrame::SetAutoDestroy.md)|Définit si la fenêtre déroulante enfant de barre d'outils est perdue automatiquement.|  
  
### Remarques  
 Cette classe n'est pas destinée à être utilisée directement à partir de votre code.  
  
 L'infrastructure utilise la classe pour fournir un comportement de frame aux classes d' `CMFCDropDownToolbar` et d' `CMFCDropDownToolbarButton` .  Pour plus d'informations sur ces classes, consultez [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) et [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## Exemple  
 L'exemple suivant montre comment récupérer un pointeur vers un objet d' `CMFCDropDownFrame` d'une classe d' `CFrameWnd` , et comment définir la fenêtre déroulante enfant de barre d'outils à détruire automatiquement.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/CPP/cmfcdropdownframe-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdropdowntoolbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)