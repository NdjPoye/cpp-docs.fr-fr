---
title: Classe de COleResizeBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
dev_langs:
- C++
helpviewer_keywords:
- OLE items, resizing
- in-place items
- in-place items, resizing
- resizing in-place OLE items
- control bars, resizing
- COleResizeBar class
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 99ba53c771d018b8c69c5951703b9d6f7b4afe9b
ms.lasthandoff: 02/24/2017

---
# <a name="coleresizebar-class"></a>COleResizeBar (classe)
Type de barre de contrôle qui prend en charge le redimensionnement des éléments OLE sur place.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|Construit un objet `COleResizeBar`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|Crée et initialise une fenêtre enfant Windows et l’associe à la `COleResizeBar` objet.|  
  
## <a name="remarks"></a>Remarques  
 `COleResizeBar`les objets apparaissent en tant qu’un [CRectTracker](../../mfc/reference/crecttracker-class.md) avec une bordure hachurée externes et des poignées de redimensionnement.  
  
 `COleResizeBar`les objets sont généralement incorporés membres des objets de fenêtre frame dérivées de la [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) classe.  
  
 Pour plus d’informations, consultez l’article [Activation](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="coleresizebar"></a>COleResizeBar::COleResizeBar  
 Construit un objet `COleResizeBar`.  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez **créer** pour créer l’objet de barre de redimensionnement.  
  
##  <a name="create"></a>COleResizeBar::Create  
 Crée une fenêtre enfant et l’associe à la `COleResizeBar` objet.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers la fenêtre parente de la barre de redimensionnement.  
  
 `dwStyle`  
 Spécifie le [style de fenêtre](../../mfc/reference/window-styles.md) attributs.  
  
 `nID`  
 ID de fenêtre enfant de la barre redimensionnement.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la barre de redimensionnement a été créée ; sinon 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar (classe)](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe de COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

