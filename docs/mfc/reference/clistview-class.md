---
title: CListView (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- CListView class
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ebf6c93aa6d88d1942af4ecb9e3373fa57d84b65
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="clistview-class"></a>CListView (classe)
Simplifie l’utilisation du contrôle de liste et de [CListCtrl](../../mfc/reference/clistctrl-class.md), la classe qui encapsule les fonctionnalités de contrôle de liste, avec l’architecture document / vue de MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CListView : public CCtrlView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CListView::CListView](#clistview)|Construit un objet `CListView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CListView::GetListCtrl](#getlistctrl)|Retourne le contrôle de liste associé à la vue.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CListView::RemoveImageList](#removeimagelist)|Supprime la liste de l’image spécifiée dans la liste.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur cette architecture, consultez la vue d’ensemble de la [CView](../../mfc/reference/cview-class.md) classe et les références croisées citées il.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcview.h  
  
##  <a name="clistview"></a>CListView::CListView  
 Construit un objet `CListView`.  
  
```  
CListView();
```  
  
##  <a name="getlistctrl"></a>CListView::GetListCtrl  
 Appelez cette fonction membre pour obtenir une référence au contrôle de liste associé à la vue.  
  
```  
CListCtrl& GetListCtrl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence au contrôle de liste associé à la vue.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCListView&#7;](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]  
  
##  <a name="removeimagelist"></a>CListView::RemoveImageList  
 Supprime la liste de l’image spécifiée dans la liste.  
  
```  
void RemoveImageList(int nImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 `nImageList`  
 Index de base zéro de l’image à supprimer.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC ROWLIST](../../visual-cpp-samples.md)   
 [Classe de CCtrlView](../../mfc/reference/cctrlview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe de CCtrlView](../../mfc/reference/cctrlview-class.md)

