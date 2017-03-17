---
title: Classe CTreeView | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeView class, common controls
- CTreeView class
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c317d91a07b5cb45b58ec4c4af2e9ee0f3b24e28
ms.lasthandoff: 02/24/2017

---
# <a name="ctreeview-class"></a>CTreeView (classe)
Simplifie l’utilisation du contrôle d’arborescence et de [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), la classe qui encapsule les fonctionnalités de contrôle d’arborescence, avec l’architecture document / vue de MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CTreeView : public CCtrlView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CTreeView::CTreeView](#ctreeview)|Construit un objet `CTreeView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](#gettreectrl)|Retourne le contrôle d’arborescence associé à la vue.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur cette architecture, consultez la vue d’ensemble de la [CView](../../mfc/reference/cview-class.md) classe et les références croisées citées il.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcview.h  
  
##  <a name="ctreeview"></a>CTreeView::CTreeView  
 Construit un objet `CTreeView`.  
  
```  
CTreeView();
```  
  
##  <a name="gettreectrl"></a>CTreeView::GetTreeCtrl  
 Retourne une référence au contrôle d’arborescence associée à la vue.  
  
```  
CTreeCtrl& GetTreeCtrl() const;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)   
 [Classe de CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl (classe)](../../mfc/reference/ctreectrl-class.md)

