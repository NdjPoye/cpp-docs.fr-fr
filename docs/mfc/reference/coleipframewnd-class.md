---
title: Classe de COleIPFrameWnd | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd class
- OLE, editing
- OLE, in-place activation
- in-place editing
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85ce028bb5d72c06a0e228abba1bd08a7f6526cb
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd (classe)
Base pour la fenêtre de modification sur place de votre application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Construit un objet `COleIPFrameWnd`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Appelé par l’infrastructure lorsqu’un élément est activé pour la modification sur place.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Appelée par l’infrastructure pour repositionner la fenêtre de modification sur place.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe crée et positions des barres dans la fenêtre de document de l’application conteneur de contrôles. Il gère également les notifications générées par incorporé [COleResizeBar](../../mfc/reference/coleresizebar-class.md) lorsque l’utilisateur redimensionne la fenêtre d’édition sur place de l’objet.  
  
 Pour plus d’informations sur l’utilisation de `COleIPFrameWnd`, consultez l’article [Activation](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="a-namecoleipframewnda--coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 Construit un `COleIPFrameWnd` de l’objet et initialise ses informations d’état de la place, ce qui sont stockées dans une structure de type **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameoncreatecontrolbarsa--coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 Le framework appelle la `OnCreateControlBars` fonctionner lorsqu’un élément est activé pour la modification sur place.  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWndFrame*  
 Pointeur vers la fenêtre frame de l’application conteneur.  
  
 *pWndDoc*  
 Pointeur vers la fenêtre du conteneur au niveau du document. Peut être **NULL** si le conteneur est une application SDI.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro en cas de réussite ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 L'implémentation par défaut n'exécute aucune opération. Remplacez cette fonction pour effectuer tout traitement spécial requis lors de la création de barres de contrôles.  
  
##  <a name="a-namerepositionframea--coleipframewndrepositionframe"></a><a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 Le framework appelle la `RepositionFrame` fonction membre pour disposer les barres de contrôles et repositionner la fenêtre de modification sur place sont visibles.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPosRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet contenant l’emplacement dans actuelle coordonnées de position la fenêtre, en pixels, par rapport à la zone cliente de trame.  
  
 `lpClipRect`  
 Pointeur vers un `RECT` structure ou un `CRect` objet contenant l’emplacement dans rectangulaire coordonnées actuelles la fenêtre, en pixels, par rapport à la zone cliente de trame.  
  
### <a name="remarks"></a>Remarques  
 Diffère de la disposition des barres de contrôle dans la fenêtre conteneur effectuées par une fenêtre frame de non-OLE. La fenêtre frame de non-OLE calcule les positions des barres de contrôles et d’autres objets à partir d’une taille de fenêtre frame donné, comme dans un appel à [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). La zone cliente est ce qui reste après la soustraction de l’espace pour les barres de contrôles et d’autres objets. Un `COleIPFrameWnd` fenêtre, positionne en revanche, les barres d’outils conformément à une zone donnée client. En d’autres termes, `CFrameWnd::RecalcLayout` fonctionne « de l’extérieur, », tandis que `COleIPFrameWnd::RepositionFrame` fonctionne « de l’intérieur. »  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFrameWnd (classe)](../../mfc/reference/cframewnd-class.md)

