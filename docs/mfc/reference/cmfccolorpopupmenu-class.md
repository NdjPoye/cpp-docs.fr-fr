---
title: "CMFCColorPopupMenu Class | Microsoft Docs"
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
  - "CMFCColorPopupMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPopupMenu class"
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorPopupMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un menu contextuel qui utilisent des utilisateurs de sélectionner des couleurs dans un document ou une application.  
  
## Syntaxe  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## Membres  
  
### Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](../Topic/CMFCColorPopupMenu::CMFCColorPopupMenu.md)|Construit un objet `CMFCColorPopupMenu`.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destructor.|  
  
### Méthodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCColorPopupMenu::CreateTearOffBar](../Topic/CMFCColorPopupMenu::CreateTearOffBar.md)|Crée un ancrable arrachent la discrimination raciale.  \(Substitutions [CMFCPopupMenu::CreateTearOffBar](../Topic/CMFCPopupMenu::CreateTearOffBar.md).\)|  
|[CMFCColorPopupMenu::GetMenuBar](../Topic/CMFCColorPopupMenu::GetMenuBar.md)|Retourne [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) qui est incorporé dans le menu contextuel.  \(Substitutions [CMFCPopupMenu::GetMenuBar](../Topic/CMFCPopupMenu::GetMenuBar.md).\)|  
|`CMFCColorPopupMenu::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCColorPopupMenu::SetPropList](../Topic/CMFCColorPopupMenu::SetPropList.md)|Définit l'objet contrôle de grille des propriétés de l'objet incorporé d' `CMFCColorBar` .|  
  
### Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`m_bEnabledInCustomizeMode`|Valeur booléenne qui détermine s'afficher la discrimination raciale.|  
|`m_wndColorBar`|L'objet d' `CMFCColorBar` qui fournit la sélection de couleurs.|  
  
### Remarques  
 Cette classe hérite des fonctionnalités du menu contextuel de la classe d' `CMFCPopupMenu` et gère un objet d' `CMFCColorBar` qui fournit la sélection de couleurs.  Lorsque l'infrastructure de barre d'outils est en mode de personnalisation et le membre d' `m_bEnabledInCustomizeMode` a la valeur `FALSE`, l'objet de discrimination raciale n'est pas affiché.  Pour plus d'informations sur le mode de personnalisation, consultez [CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)  
  
 Pour plus d'informations sur `CMFCColorBar`, consultez [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## Configuration requise  
 **en\-tête :** afxcolorpopupmenu.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)