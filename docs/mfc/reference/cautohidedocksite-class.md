---
title: Classe de CAutoHideDockSite | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AllowShowOnPaneMenu
- CAutoHideDockSite::AllowShowOnPaneMenu
- CAutoHideDockSite.AllowShowOnPaneMenu
dev_langs:
- C++
helpviewer_keywords:
- AllowShowOnPaneMenu method
- CAutoHideDockSite class
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
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
ms.openlocfilehash: 58beaa382a2ef04cfaee0fbcf63b9eef36831472
ms.lasthandoff: 02/24/2017

---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite (classe)
Le `CAutoHideDockSite` étend la [CDockSite classe](../../mfc/reference/cdocksite-class.md) pour implémenter des volets d’ancrage masquage automatique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CAutoHideDockSite::CAutoHideDockSite`|Construit un objet `CAutoHideDockSite`.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Indique si la `CAutoHideDockSite` est affiché dans le menu du volet.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Détermine si un objet de base de volet est dérivé le [CMFCAutoHideBar classe](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Ancre un volet à ce `CAuotHideDockSite` objet.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Récupère la taille du site d’ancrage en coordonnées d’écran.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Redessine le volet sur la `CAutoHideDockSite` avec les marges globales et l’espacement du bouton.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Définit la marge à gauche de la barre d’ancrage.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Définit la marge à droite de la barre d’ancrage.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Appels [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) pour les objets sur le `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Définit la taille de l’espace entre les barres d’outils et le bord de la barre d’ancrage. Cet espace est mesuré à partir du bord gauche ou le bord supérieur, en fonction de l’alignement de l’espace d’ancre.|  
  
## <a name="remarks"></a>Remarques  
 Lorsque vous appelez [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), l’infrastructure crée automatiquement un `CAutoHideDockSite` objet. Dans la plupart des cas, vous devez pas instancier ou utiliser directement cette classe.  
  
 La barre d’ancrage est la différence entre le côté gauche du volet d’ancrage et le côté gauche de la [CMFCAutoHideButton classe](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment récupérer un `CAutoHideDockSite` de l’objet d’un `CMFCAutoHideBar` objet et comment définir les marges gauche et droite de la barre d’ancrage.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#29;](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxautohidedocksite.h  
  
##  <a name="a-namecanacceptpanea--cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 Détermine si un volet de base est un [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) de l’objet ou dérivé de `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pBar`|Le volet de base qui teste l’infrastructure.|  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si `pBar` est dérivée de `CMFCAutoHideBar`; `FALSE` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Si un objet de base de volet est dérivé de `CMFCAutoHideBar`, il peut contenir un `CAutoHideDockSite`.  
  
##  <a name="a-namedockpanea--cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDockSite::DockPane  
 Ancre un volet à ce [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) objet.  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pWnd`|Le volet de l’infrastructure est ancré.|  
|[in] `dockMethod`|Stations d’accueil pour le volet.|  
|[in] `lpRect`|Rectangle qui spécifie les limites du volet ancré.|  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut n’utilise pas le paramètre `dockMethod`, qui est fourni pour une utilisation ultérieure.  
  
 Si `lpRect` est `NULL`, elle place le volet de l’emplacement par défaut sur le site d’ancrage. Si le site d’ancrage est horizontal, l’emplacement par défaut est à l’extrême gauche du site d’ancrage. Dans le cas contraire, l’emplacement par défaut est en haut du site d’ancrage.  
  
##  <a name="a-namegetalignrecta--cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 Récupère la taille du site d’ancrage en coordonnées d’écran.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `rect`|Une référence à un rectangle. La méthode stocke la taille du site d’ancrage dans ce rectangle.|  
  
### <a name="remarks"></a>Notes  
 Le rectangle est ajusté pour les marges de décalage, afin qu’ils ne sont pas inclus.  
  
##  <a name="a-namemnextraspacea--cautohidedocksitemnextraspace"></a><a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 La taille de l’espace entre les bords de la [CAutoHideDockSite classe](../../mfc/reference/cautohidedocksite-class.md) et [CMFCAutoHideBar classe](../../mfc/reference/cmfcautohidebar-class.md) objets.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Notes  
 Lorsqu’un `CMFCAutoHideBar` est ancré à un `CAutoHideDockSite`, doit occuper pas le site d’ancrage entière. Cette variable globale contrôle l’espace supplémentaire entre le bord gauche ou supérieur de la `CMFCAutoHideBar` et `CAutoHideDockSite` edge. Si le bord supérieur ou gauche est utilisé dépend de l’alignement actuel.  
  
##  <a name="a-namesetoffsetlefta--cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 Définit la marge à gauche de la barre d’ancrage.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nOffset`  
 Le décalage de nouveau.  
  
### <a name="remarks"></a>Notes  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) les objets sont positionnés statiquement dans le `CAutoHideDockSite` objet. Cela signifie que l’utilisateur ne peut pas modifier manuellement l’emplacement de `CMFCAutoHideBar` objets. Le `SetOffsetLeft` méthode contrôle la distance entre le côté gauche de l’extrême gauche `CMFCAutoHideBar` et le côté gauche de la `CAutoHideDockSite`.  
  
##  <a name="a-namesetoffsetrighta--cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 Définit la marge à droite de la barre d’ancrage.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nOffset`  
 Le décalage de nouveau.  
  
### <a name="remarks"></a>Remarques  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) les objets sont positionnés statiquement dans le `CAutoHideDockSite` objet. Cela signifie que l’utilisateur ne peut pas modifier manuellement l’emplacement de la `CMFCAutoHideBar` objets. Le `SetOffsetRight` méthode contrôle la distance entre le côté droit de la plus à droite `CMFCAutoHideBar` et le côté droit de la `CAutoHideDockSite`.  
  
##  <a name="a-namerepositionpanesa--cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 Redessine les volets sur le [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `rectNewClientArea`|Une valeur réservée.|  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut n’utilise pas `rectNewClientArea`. Il redessine les volets avec les marges de la barre d’outils globale et l’espacement du bouton.  
  
##  <a name="a-nameunsetautohidemodea--cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 Appels [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) pour les objets sur le site d’ancrage.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pAutoHideToolbar`|Un pointeur vers un [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) objet volet situé sur le `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Remarques  
 Cette méthode recherche la ligne qui contient `pAutoHideToolbar`. Il appelle `CMFCAutoHideBar.UnSetAutoHideMode` pour toutes les `CMFCAutoHideBar` objets sur cette ligne. Si `pAutoHideToolbar` est introuvable ou il est `NULL`, cette méthode appelle `CMFCAutoHideBar.UnSetAutoHideMode` pour tous les le `CMFCAutoHideBar` des objets sur le `CAutoHideDockSite`.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockSite (classe)](../../mfc/reference/cdocksite-class.md)

