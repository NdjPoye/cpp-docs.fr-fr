---
title: "CMFCRibbonMiniToolBar Class | Microsoft Docs"
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
  - "CMFCRibbonMiniToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMiniToolBar class"
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonMiniToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une barre d'outils contextuelle.  
  
## Syntaxe  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Constructeur par défaut.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destructeur.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](../Topic/CMFCRibbonMiniToolBar::IsContextMenuMode.md)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](../Topic/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar.md)|\(Substitue `CMFCPopupMenu::IsRibbonMiniToolBar`.\)|  
|[CMFCRibbonMiniToolBar::SetCommands](../Topic/CMFCRibbonMiniToolBar::SetCommands.md)|Définit la liste des commandes à afficher sur la barre d'outils.|  
|[CMFCRibbonMiniToolBar::Show](../Topic/CMFCRibbonMiniToolBar::Show.md)|Affiche la mini\-barre d'outils au niveau des coordonnées d'écran spécifiées.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](../Topic/CMFCRibbonMiniToolBar::ShowWithContextMenu.md)|Affiche la mini\-barre d'outils avec un menu contextuel.|  
  
## Notes  
 La mini\-barre d'outils s'affiche généralement après que l'utilisateur sélectionne un objet dans un document.  Ainsi, quand l'utilisateur sélectionne un bloc de texte dans un programme de traitement de texte, l'application affiche une mini\-barre d'outils qui contient des commandes de mise en forme de texte.  
  
 La mini\-barre d'outils devient transparente quand le pointeur de la souris sort des limites de la mini\-barre d'outils.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## Configuration requise  
 **En\-tête :** afxRibbonMiniToolBar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)