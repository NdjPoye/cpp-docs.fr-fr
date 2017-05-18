---
title: "Styles utilisés par MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.styles
dev_langs:
- C++
helpviewer_keywords:
- edit styles [MFC]
- window styles, in MFC
- styles
- frame windows, styles
- message-box styles
- styles, MFC
- buttons, MFC toolbars
- list boxes, styles
- static styles
- scroll-bar styles [MFC]
- combo boxes, styles
- extended window styles
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 344d2ce3de15403e17f29dc9504253cbb0ade607
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="styles-used-by-mfc"></a>Styles utilisés par MFC
Utiliser les styles suivants lorsque vous créez l’objet MFC correspondant. Dans la plupart des cas, ces styles sont définies dans le `dwStyle` paramètre de la classe **créer** (fonction).  
  
### <a name="mfc-styles"></a>Styles de MFC  
  
|Style|Description|  
|-----------|-----------------|  
|[Styles des boutons](../../mfc/reference/button-styles.md)|S’applique aux [CButton classe](../../mfc/reference/cbutton-class.md) objets, tels que des cases d’option, cases à cocher et boutons de commande. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CButton::Create](../../mfc/reference/cbutton-class.md#create).|  
|[Styles de zone de liste déroulante](../../mfc/reference/combo-box-styles.md)|S’applique aux [CComboBox (classe)](../../mfc/reference/ccombobox-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CComboBox::Create](../../mfc/reference/ccombobox-class.md#create).|  
|[Modifier les styles](../../mfc/reference/edit-styles.md)|S’applique aux [classe CEdit](../../mfc/reference/cedit-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CEdit::Create](../../mfc/reference/cedit-class.md#create).|  
|[Styles de fenêtre frame](../../mfc/reference/frame-window-styles-mfc.md)|S’applique aux [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create).|  
|[Styles de zone de liste](../../mfc/reference/list-box-styles.md)|S’applique aux [CListBox (classe)](../../mfc/reference/clistbox-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CListBox::Create](../../mfc/reference/clistbox-class.md#create).|  
|[Styles de zone de message](../../mfc/reference/message-box-styles.md)|S’applique aux [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) éléments. Spécifier une combinaison de styles dans le `nType` paramètre de `AfxMessageBox`.|  
|[Styles de barre de défilement](../../mfc/reference/scroll-bar-styles.md)|S’applique aux [CScrollBar classe](../../mfc/reference/cscrollbar-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create).|  
|[Styles statiques](../../mfc/reference/static-styles.md)|S’applique aux [CStatic classe](../../mfc/reference/cstatic-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CStatic::Create](../../mfc/reference/cstatic-class.md#create).|  
|[Styles de fenêtre](../../mfc/reference/window-styles.md)|S’applique aux [classe CWnd](../../mfc/reference/cwnd-class.md) objets. Spécifier une combinaison de styles dans le `dwStyle` paramètre de [CWnd::Create](../../mfc/reference/cwnd-class.md#create) ou [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
|[Styles de fenêtre étendus](../../mfc/reference/extended-window-styles.md)|S’applique aux [classe CWnd](../../mfc/reference/cwnd-class.md) objets. Spécifier une combinaison de styles dans le `dwExStyle` paramètre de [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex).|  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../mfc/class-library-overview.md)


