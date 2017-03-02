---
title: Classe de CMFCBaseToolBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCBaseToolBar::CreateObject
- ~CMFCBaseToolBar
- CMFCBaseToolBar
- CMFCBaseToolBar::CMFCBaseToolBar
- CMFCBaseToolBar::~CMFCBaseToolBar
- CMFCBaseToolBar.~CMFCBaseToolBar
- CreateObject
- CMFCBaseToolBar.CMFCBaseToolBar
- CMFCBaseToolBar.CreateObject
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseToolBar class, constructor
- CMFCBaseToolBar class, destructor
- ~CMFCBaseToolBar destructor
- CreateObject method
- CMFCBaseToolBar class
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: 19
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
ms.openlocfilehash: f608b23c0dbee3ec0e2d2b234612365e3c2461b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar (classe)
Classe de base pour les barres d’outils.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|Constructeur par défaut.|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCBaseToolBar::GetDockingMode](#getdockingmode)|Retourne le mode d'ancrage. (Substitue [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|  
|[CMFCBaseToolBar::GetMinSize](#getminsize)|Retourne la taille minimale d’une barre d’outils. (Substitue [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CMFCBaseToolBar::OnAfterChangeParent](#onafterchangeparent)|Appelé par l’infrastructure après modification du parent du volet. (Substitue [CBasePane::OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxbasetoolbar.h  
  
##  <a name="a-namegetdockingmodea--cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a>CMFCBaseToolBar::GetDockingMode  
 Retourne le mode d'ancrage.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode d’ancrage.  
  
##  <a name="a-namegetminsizea--cmfcbasetoolbargetminsize"></a><a name="getminsize"></a>CMFCBaseToolBar::GetMinSize  
 Retourne la taille minimale d’une barre d’outils.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `size`  
 La taille minimale d’une barre d’outils.  
  
##  <a name="a-nameonafterchangeparenta--cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a>CMFCBaseToolBar::OnAfterChangeParent  
 Appelé par l’infrastructure après modification du parent du volet.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndOldParent`  
 Pointeur vers la fenêtre parente précédente.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

