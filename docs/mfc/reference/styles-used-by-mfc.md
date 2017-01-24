---
title: "Styles utilis&#233;s par MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.styles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boutons, barres d'outils MFC"
  - "zones de liste déroulante, styles"
  - "modifier les styles (MFC)"
  - "styles de fenêtre étendus"
  - "fenêtres frame, styles"
  - "zones de liste, styles"
  - "styles de boîte de message"
  - "styles de barre de défilement (MFC)"
  - "styles statiques"
  - "styles"
  - "styles, MFC"
  - "styles de fenêtres, dans MFC"
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles utilis&#233;s par MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez les styles suivants lorsque vous créez l'objet MFC correspondant.  Dans la plupart des cas, ces styles sont définis dans le paramètre `dwStyle` de la fonction de classe **Créer** .  
  
### ..\/styles\/{0}  
  
|Style|Description|  
|-----------|-----------------|  
|[Styles des boutons](../../mfc/reference/button-styles.md)|Applique aux [Classe de CButton](../../mfc/reference/cbutton-class.md) des objets, tels que les cases d'option, les cases à cocher et les boutons poussoirs.  Spécifiez une combinaison de styles dans le paramètre d' `dwStyle` [CButton::Create](../Topic/CButton::Create.md).|  
|[Styles de zone de liste déroulante](../../mfc/reference/combo-box-styles.md)|Applique à la [Classe de CComboBox](../../mfc/reference/ccombobox-class.md) des objets.  Spécifiez une combinaison de styles dans le paramètre d' `dwStyle` [CComboBox::Create](../Topic/CComboBox::Create.md).|  
|[Modifier les styles](../../mfc/reference/edit-styles.md)|Applique à [Classe d'objets de CEdit](../../mfc/reference/cedit-class.md).  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CButton::Create](../Topic/CEdit::Create.md).|  
|[Styles des cadres des fenêtres](../../mfc/reference/frame-window-styles-mfc.md)|Applique à [Classe d'objets de CFrameWnd](../../mfc/reference/cframewnd-class.md).  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CComboBox::Create](../Topic/CFrameWnd::Create.md).|  
|[Styles des zones des listes](../../mfc/reference/list-box-styles.md)|Applique à [Classe d'objets de CListBox](../../mfc/reference/clistbox-class.md).  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CComboBox::Create](../Topic/CListBox::Create.md).|  
|[Styles des fenêtres des messages](../../mfc/reference/message-box-styles.md)|Applique à [AfxMessageBox](../Topic/AfxMessageBox.md) des éléments.  Spécifiez une combinaison des styles dans le paramètre `nType` de `AfxMessageBox`.|  
|[Styles des barres de défilement](../../mfc/reference/scroll-bar-styles.md)|Applique à [Classe des objets de CScrollBar](../../mfc/reference/cscrollbar-class.md).  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CComboBox::Create](../Topic/CScrollBar::Create.md).|  
|[Styles statiques](../../mfc/reference/static-styles.md)|Applique à [la Classe des objets CStatic](../../mfc/reference/cstatic-class.md).  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CButton::Create](../Topic/CStatic::Create.md).|  
|[Styles de fenêtre](../../mfc/reference/window-styles.md)|[S'applique aux éléments suivants:](../../mfc/reference/cwnd-class.md) classe, propriété.  Spécifiez une combinaison de styles dans le paramètre `dwStyle` [CComboBox::Create](../Topic/CWnd::Create.md).|  
|[Styles de fenêtre avancés](../../mfc/reference/extended-window-styles.md)|S'applique aux éléments [suivants](../../mfc/reference/cwnd-class.md) classe, propriété.  Spécifiez une combinaison de styles dans le paramètre `dwExStyle` de [CButton::Create](../Topic/CWnd::CreateEx.md).|  
  
## Voir aussi  
 [Vue d'ensemble des classes](../../mfc/class-library-overview.md)