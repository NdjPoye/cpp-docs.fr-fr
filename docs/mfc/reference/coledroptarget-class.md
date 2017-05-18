---
title: Classe de COleDropTarget | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget class
- drag and drop, drop target
- drop commands, accepting
- drop commands
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0e9429d531d6af86bc571b1f871fbcd4a8fe2532
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coledroptarget-class"></a>COleDropTarget (classe)
Fournit le mécanisme de communication entre une fenêtre et les bibliothèques OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|Construit un objet `COleDropTarget`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|Appelé lorsque le curseur entre d’abord dans la fenêtre.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|Appelé lorsque le curseur est déplacé en dehors de la fenêtre.|  
|[COleDropTarget::OnDragOver](#ondragover)|Appelée à plusieurs reprises lorsque le curseur est déplacé au-dessus de la fenêtre.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|Appelée pour déterminer si le curseur est déplacé dans la zone de défilement de la fenêtre.|  
|[COleDropTarget::OnDrop](#ondrop)|Appelé lorsque les données sont déplacées dans la fenêtre, le gestionnaire par défaut.|  
|[COleDropTarget::OnDropEx](#ondropex)|Appelé lorsque les données sont déposées dans la fenêtre Gestionnaire initiale.|  
|[COleDropTarget::Register](#register)|Enregistre la fenêtre comme cible de déplacement valide.|  
|[COleDropTarget::Revoke](#revoke)|La fenêtre de cesser d’être une cible de déplacement valide.|  
  
## <a name="remarks"></a>Remarques  
 Création d’un objet de cette classe permet à une fenêtre accepter les données par le biais du mécanisme de glisser-déplacer OLE.  
  
 Pour obtenir une fenêtre pour accepter les commandes de menu, vous devez d’abord créer un objet de la `COleDropTarget` de classe, puis appelez le [enregistrer](#register) fonction avec un pointeur vers l’élément `CWnd` objet comme seul paramètre.  
  
 Pour plus d’informations sur les opérations de glisser-déplacer à l’aide de OLE, consultez l’article [glisser-déplacer (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="coledroptarget"></a>COleDropTarget::COleDropTarget  
 Construit un objet de classe `COleDropTarget`.  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez [enregistrer](#register) associer cet objet à une fenêtre.  
  
##  <a name="ondragenter"></a>COleDropTarget::OnDragEnter  
 Appelé par l’infrastructure lorsque le curseur est déplacé tout d’abord dans la fenêtre.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers la fenêtre du curseur est saisie.  
  
 `pDataObject`  
 Pointe vers l’objet de données contenant les données qui peuvent être supprimées.  
  
 `dwKeyState`  
 Contient l’état des touches de modification. Il s’agit d’une combinaison d’un nombre quelconque des valeurs suivantes : **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, et **MK_RBUTTON**.  
  
 `point`  
 Contient l’emplacement actuel du curseur en coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 L’effet que si une liste a été tentée à l’emplacement spécifié par `point`. Il peut être une ou plusieurs des opérations suivantes :  
  
- `DROPEFFECT_NONE`Une liste ne serait pas autorisée.  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
- `DROPEFFECT_SCROLL`Une opération glisser de défilement est sur le point de se produire ou se produit dans la cible.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction pour permettre les opérations de suppression dans la fenêtre. L’implémentation par défaut appelle [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), qui renvoie simplement `DROPEFFECT_NONE` par défaut.  
  
 Pour plus d’informations, consultez [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 Appelé par l’infrastructure lorsque le curseur quitte la fenêtre pendant une opération de glisser-déplacer est en vigueur.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers la fenêtre le curseur quitte.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction si vous souhaitez un comportement spécial lorsque l’opération de déplacement quitte la fenêtre spécifiée. L’implémentation par défaut de cette fonction appelle [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Pour plus d’informations, consultez [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondragover"></a>COleDropTarget::OnDragOver  
 Appelé par l’infrastructure lorsque le curseur est déplacé au-dessus de la fenêtre.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers la fenêtre qui est placé le curseur.  
  
 `pDataObject`  
 Pointe vers l’objet de données qui contient les données à supprimer.  
  
 `dwKeyState`  
 Contient l’état des touches de modification. Il s’agit d’une combinaison d’un nombre quelconque des valeurs suivantes : **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, et **MK_RBUTTON**.  
  
 `point`  
 Contient l’emplacement actuel du curseur en coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 L’effet que si une liste a été tentée à l’emplacement spécifié par `point`. Il peut être une ou plusieurs des opérations suivantes :  
  
- `DROPEFFECT_NONE`Une liste ne serait pas autorisée.  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
- `DROPEFFECT_SCROLL`Indique qu’une opération glisser de défilement est sur le point de se produire ou se produit dans la cible.  
  
### <a name="remarks"></a>Notes  
 Cette fonction doit être substituée pour permettre les opérations de suppression dans la fenêtre. L’implémentation par défaut de cette fonction appelle [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), qui renvoie `DROPEFFECT_NONE` par défaut. Étant donné que cette fonction est appelée fréquemment pendant une opération de glisser-déplacer, il doit être optimisée autant que possible.  
  
 Pour plus d’informations, consultez [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCOleContainer n °&21;](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 Appelé par l’infrastructure avant d’appeler [OnDragEnter](#ondragenter) ou [OnDragOver](#ondragover) pour déterminer si `point` se trouve dans la zone de défilement.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Dans la fenêtre, sur que le curseur se trouve actuellement les points.  
  
 `dwKeyState`  
 Contient l’état des touches de modification. Il s’agit d’une combinaison d’un nombre quelconque des valeurs suivantes : **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, et **MK_RBUTTON**.  
  
 `point`  
 Contient l’emplacement du curseur, en pixels, par rapport à l’écran.  
  
### <a name="return-value"></a>Valeur de retour  
 L’effet que si une liste a été tentée à l’emplacement spécifié par `point`. Il peut être une ou plusieurs des opérations suivantes :  
  
- `DROPEFFECT_NONE`Une liste ne serait pas autorisée.  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
- `DROPEFFECT_SCROLL`Indique qu’une opération glisser de défilement est sur le point de se produire ou se produit dans la cible.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction lorsque vous souhaitez fournir un comportement spécial pour cet événement. L’implémentation par défaut de cette fonction appelle [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), qui renvoie `DROPEFFECT_NONE` et fait défiler la fenêtre lorsque le curseur est déplacé dans la zone de défilement par défaut à l’intérieur de la bordure de la fenêtre.  
  
##  <a name="ondrop"></a>COleDropTarget::OnDrop  
 Appelé par l’infrastructure lorsqu’une opération de suppression doit se produire.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Dans la fenêtre, sur que le curseur se trouve actuellement les points.  
  
 `pDataObject`  
 Pointe vers l’objet de données qui contient les données à supprimer.  
  
 `dropEffect`  
 L’effet que l’utilisateur a choisi pour l’opération de suppression. Il peut être une ou plusieurs des opérations suivantes :  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
 `point`  
 Contient l’emplacement du curseur, en pixels, par rapport à l’écran.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la suppression a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle d’abord [OnDropEx](#ondropex). Si le `OnDropEx` (fonction) ne gère pas la liste déroulante, le framework appelle ensuite cette fonction membre, `OnDrop`. En règle générale, l’application remplace [OnDropEx](../../mfc/reference/cview-class.md#ondropex) dans la classe d’affichage pour gérer le bouton droit de la souris, faites glisser-déplacer. En règle générale, la classe d’affichage [OnDrop](../../mfc/reference/cview-class.md#ondrop) est utilisée pour gérer de simples glisser -déplacer.  
  
 L’implémentation par défaut de `COleDropTarget::OnDrop` appelle [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), qui renvoie simplement **FALSE** par défaut.  
  
 Pour plus d’informations, consultez [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ondropex"></a>COleDropTarget::OnDropEx  
 Appelé par l’infrastructure lorsqu’une opération de suppression doit se produire.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Dans la fenêtre, sur que le curseur se trouve actuellement les points.  
  
 `pDataObject`  
 Pointe vers l’objet de données qui contient les données à supprimer.  
  
 `dropDefault`  
 L’effet que l’utilisateur a choisi pour l’opération de suppression par défaut en fonction de l’état actuel de la clé. Il peut être `DROPEFFECT_NONE`. Effets de déplacement sont décrites dans la section Notes.  
  
 `dropList`  
 Une liste des effets de déplacement qui prend en charge de la source de déplacement. Valeurs d’effet de déplacement peuvent être combinées à l’aide de l’opérateur de bits OR ( **|**) opération. Effets de déplacement sont décrites dans la section Notes.  
  
 `point`  
 Contient l’emplacement du curseur, en pixels, par rapport à l’écran.  
  
### <a name="return-value"></a>Valeur de retour  
 L’effet résultant de la tentative de suppression à l’emplacement spécifié par `point`. Effets de déplacement sont décrites dans la section Notes.  
  
### <a name="remarks"></a>Remarques  
 Tout d’abord, l’infrastructure appelle cette fonction. Si elle ne gère pas la liste déroulante, le framework appelle [OnDrop](#ondrop). En règle générale, vous devez substituer [OnDropEx](../../mfc/reference/cview-class.md#ondropex) dans la classe d’affichage pour prendre en charge le bouton droit de la souris, faites glisser-déplacer. En règle générale, la classe d’affichage [OnDrop](../../mfc/reference/cview-class.md#ondrop) est utilisé pour gérer le cas de prise en charge d’un simple glisser -déplacer.  
  
 L’implémentation par défaut de `COleDropTarget::OnDropEx` appelle [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). Par défaut, [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) renvoie simplement une valeur factice pour indiquer la [OnDrop](#ondrop) fonction membre doit être appelée.  
  
 Effets de déplacement décrivent l’action associée à une opération de suppression. Consultez la liste suivante des effets de déplacement :  
  
- `DROPEFFECT_NONE`Une liste ne serait pas autorisée.  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
- `DROPEFFECT_SCROLL`Indique qu’une opération glisser de défilement est sur le point de se produire ou se produit dans la cible.  
  
 Pour plus d’informations, consultez [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="register"></a>COleDropTarget::Register  
 Appelez cette fonction pour inscrire votre fenêtre avec les DLL OLE comme cible de déplacement valide.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers la fenêtre doit être enregistré en tant que cible de dépôt.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’inscription a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction doit être appelée pour les opérations de suppression d’être acceptés.  
  
 Pour plus d’informations, consultez [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="revoke"></a>COleDropTarget::Revoke  
 Appelez cette fonction avant de détruire les fenêtres qui a été enregistré en tant que cible de dépôt via un appel à [enregistrer](#register) à supprimer de la liste des cibles de dépôt.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée automatiquement à partir de la [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) gestionnaire pour la fenêtre qui a été enregistrée, donc il n’est généralement pas nécessaire d’appeler cette fonction explicitement.  
  
 Pour plus d’informations, consultez [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC HIERSVR](../../visual-cpp-samples.md)   
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDropSource (classe)](../../mfc/reference/coledropsource-class.md)

