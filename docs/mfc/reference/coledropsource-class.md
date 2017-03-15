---
title: Classe de COleDropSource | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropSource
dev_langs:
- C++
helpviewer_keywords:
- drag operations
- drop target, dragging data to
- COleDropSource class
- drag and drop, drop source
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f3d0e5b7184cf305459173065b8e1cc07e032aef
ms.lasthandoff: 02/24/2017

---
# <a name="coledropsource-class"></a>COleDropSource (classe)
Permet de faire glisser vers une cible de déplacement des données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|Construit un objet `COleDropSource`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|Modifie le curseur pendant une opération de glisser-déplacer.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Gère la capture de la souris pendant une opération de glisser-déplacer.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Vérifie si le glissement doit continuer.|  
  
## <a name="remarks"></a>Remarques  
 Le [COleDropTarget](../../mfc/reference/coledroptarget-class.md) classe gère la partie réception de l’opération de glisser-déplacer. Le `COleDropSource` objet est chargé de déterminer quand une opération de glisser-déplacer commence, commentaires pendant l’opération glisser et déterminer quand l’opération de glissement se termine.  
  
 Pour utiliser un `COleDropSource` de l’objet, appelez simplement le constructeur. Cela simplifie le processus permettant de déterminer quels événements, tels qu’un clic de souris, commencent une opération de glissement à l’aide de [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), ou [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) (fonction). Ces fonctions créera un `COleDropSource` objet pour vous. Vous pouvez souhaiter modifier le comportement par défaut de le `COleDropSource` fonctions substituables. Ces fonctions membres s’appellera aux moments appropriés par le framework.  
  
 Pour plus d’informations sur les opérations de glisser-déplacer à l’aide de OLE, consultez l’article [glisser-déplacer (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Pour plus d’informations, consultez [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="a-namecoledropsourcea--coledropsourcecoledropsource"></a><a name="coledropsource"></a>COleDropSource::COleDropSource  
 Construit un objet `COleDropSource`.  
  
```  
COleDropSource();
```  
  
##  <a name="a-namegivefeedbacka--coledropsourcegivefeedback"></a><a name="givefeedback"></a>COleDropSource::GiveFeedback  
 Appelé par l’infrastructure après avoir appelé [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) ou [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Paramètres  
 `dropEffect`  
 L’effet que vous souhaitez afficher à l’utilisateur, généralement en indiquant ce qui se passe si une opération déplacer est effectuée à ce stade, les données sélectionnées. Il s’agit généralement de la valeur retournée par le dernier appel à [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) ou [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Il peut être une ou plusieurs des opérations suivantes :  
  
- `DROPEFFECT_NONE`Une liste ne serait pas autorisée.  
  
- `DROPEFFECT_COPY`Une opération de copie doit être effectuée.  
  
- `DROPEFFECT_MOVE`Une opération de déplacement doit être effectuée.  
  
- `DROPEFFECT_LINK`Serait d’établir un lien entre les données déplacées et les données d’origine.  
  
- `DROPEFFECT_SCROLL`Une opération glisser de défilement est sur le point de se produire ou se produit dans la cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **DRAGDROP_S_USEDEFAULTCURSORS** si le déplacement est en cours, **NOERROR** si elle n’est pas.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour fournir des commentaires à l’utilisateur sur ce qui se passerait si une opération déplacer est effectuée à ce stade. L’implémentation par défaut utilise des curseurs OLE par défaut. Pour plus d’informations sur les opérations de glisser-déplacer à l’aide de OLE, consultez l’article [glisser-déplacer (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Pour plus d’informations, consultez [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), et [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameonbegindraga--coledropsourceonbegindrag"></a><a name="onbegindrag"></a>COleDropSource::OnBeginDrag  
 Appelée par l’infrastructure lorsque survient un événement qui pourrait commencer une opération glisser, telles que le bouton gauche de la souris.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers la fenêtre qui contient les données sélectionnées.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le glissement est autorisée, sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction si vous souhaitez modifier la manière dont le processus de déplacement est démarré. L’implémentation par défaut capture la souris et reste en mode glisser jusqu'à ce que l’utilisateur clique sur le bouton gauche ou droit de la souris ou appuie sur ÉCHAP, le moment auquel il relâche la souris.  
  
##  <a name="a-namequerycontinuedraga--coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag  
 Lorsque vous commencez, cette fonction est appelée plusieurs fois par l’infrastructure jusqu'à ce que l’opération glisser soit annulée ou terminée.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Paramètres  
 *bEscapePressed*  
 Indique si la touche ÉCHAP a été enfoncée depuis le dernier appel à `COleDropSource::QueryContinueDrag`.  
  
 `dwKeyState`  
 Contient l’état des touches de modification du clavier. Il s’agit d’une combinaison d’un nombre quelconque des valeurs suivantes : **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_MBUTTON**, et **MK_RBUTTON**.  
  
### <a name="return-value"></a>Valeur de retour  
 **DRAGDROP_S_CANCEL** si vous appuyez sur la touche ÉCHAP ou le bouton droit ou gauche est déclenché avant de faire glisser commence. **DRAGDROP_S_DROP** si une opération de suppression doit avoir lieu. Dans le cas contraire `S_OK`.  
  
### <a name="remarks"></a>Notes  
 Remplacer que cette fonction si vous souhaitez modifier le point en les faisant glisser est annulée ou une suppression se produit.  
  
 L’implémentation par défaut déclenche la liste déroulante ou annule l’opération glisser comme suit. Elle annule une opération de glisser-déplacer lorsque la touche ÉCHAP ou sur le bouton droit de la souris est enfoncé. Commence une opération de suppression lorsque le bouton gauche de la souris est déclenché après le démarrage de glissement. Sinon, elle retourne `S_OK` et n’exécute aucune opération supplémentaire.  
  
 Étant donné que cette fonction est appelée fréquemment, il doit être optimisée autant que possible.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC HIERSVR](../../visual-cpp-samples.md)   
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




