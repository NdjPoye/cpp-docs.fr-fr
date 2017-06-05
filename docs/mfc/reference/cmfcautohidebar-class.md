---
title: Classe de CMFCAutoHideBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideToolBar class
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
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
ms.openlocfilehash: db15fc9fa3925230e372b6e13368f455dcfbb1a9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar (classe)
`CMFCAutoHideBar` est une classe de barre d'outils spéciale qui implémente la fonctionnalité de masquage automatique.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Substitue `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Substitue [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCAutoHideBar::Create](#create)|Crée une barre de contrôle et l’attache à la [CPane](../../mfc/reference/cpane-class.md) objet. (Substitue [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Appelé par l'infrastructure quand un menu de volet spécial va être affiché. (Substitue [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Substitue [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Étire un volet sur le plan vertical ou horizontal. (Substitue [CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Le délai entre le moment lorsque l’utilisateur place le curseur de la souris sur un [CMFCAutoHideButton classe](../../mfc/reference/cmfcautohidebutton-class.md) et le moment lorsque le framework affiche la fenêtre associée.|  
  
## <a name="remarks"></a>Remarques  
 Quand l'utilisateur passe d'un volet d'ancrage à un mode de masquage automatique, l'infrastructure crée automatiquement un objet `CMFCAutoHideBar`. Il crée également le nécessaire [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) et [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) objets. Chaque objet `CAutoHideDockSite` est associé à un `CMFCAutoHideButton` individuel.  
  
 La classe `CMFCAutoHideBar` implémente l'affichage d'un `CAutoHideDockSite` quand l'utilisateur pointe la souris sur un `CMFCAutoHideButton`. Quand la barre d'outils reçoit un message WM_MOUSEMOVE, `CMFCAutoHideBar` démarre un minuteur. Celui-ci envoie une notification d'événement WM_TIMER à la barre d'outils à la fin du processus. La barre d'outils traite cet événement en vérifiant si le pointeur de la souris est positionné sur le même bouton de masquage automatique qu'au moment où le minuteur a démarré. Si c'est le cas, le `CAutoHideDockSite` attaché s'affiche.  
  
 Vous pouvez contrôler le délai du minuteur en définissant `m_nShowAHWndDelay`. La valeur par défaut est de 400 ms.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment construire un objet `CMFCAutoHideBar` et utiliser sa méthode `GetDockSiteRow`.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#26;](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>CMFCAutoHideBar::AddAutoHideWindow  
 Ajoute des fonctionnalités à une fenêtre `CDockablePane` , ce qui lui permet de se masquer automatiquement.  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pAutoHideWnd`  
 Fenêtre que vous souhaitez masquer.  
  
 [in] `dwAlignment`  
 Valeur qui spécifie l’alignement du bouton Masquer automatiquement par rapport à la fenêtre d’application.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
 Le paramètre `dwAlignment` indique l’emplacement du bouton Masquer automatiquement dans l’application. Le paramètre peut avoir l’une des valeurs suivantes :  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="allowshowonpanemenu"></a>CMFCAutoHideBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="calcfixedlayout"></a>CMFCAutoHideBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="cmfcautohidebar"></a>CMFCAutoHideBar::CMFCAutoHideBar  
 Construit un objet CMFCAutoHideBar.  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="create"></a>CMFCAutoHideBar::Create  

  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszClassName`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `nID`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getfirstahwindow"></a>CMFCAutoHideBar::GetFirstAHWindow  
 Retourne un pointeur vers la première fenêtre à masquage automatique de l’application.  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première fenêtre à masquage automatique de l’application, ou NULL si elle n’existe pas.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getvisiblecount"></a>CMFCAutoHideBar::GetVisibleCount  
 Obtient le nombre de boutons Masquer automatiquement visibles.  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de boutons Masquer automatiquement visibles.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_nshowahwnddelay"></a>CMFCAutoHideBar::m_nShowAHWndDelay  
 Le délai entre le moment lorsque l’utilisateur place le curseur de la souris sur un [CMFCAutoHideButton classe](../../mfc/reference/cmfcautohidebutton-class.md) et le moment lorsque le framework affiche la fenêtre associée.  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>Remarques  
 Lorsque l’utilisateur place le curseur de la souris sur un `CMFCAutoHideButton`, il existe un léger délai avant que le framework affiche la fenêtre associée. Ce paramètre détermine la longueur de ce délai en millisecondes.  
  
##  <a name="onshowcontrolbarmenu"></a>CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CPoint`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="removeautohidewindow"></a>CMFCAutoHideBar::RemoveAutoHideWindow  
 Supprime et détruit la fenêtre à masquage automatique.  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 CDockablePane *`pAutoHideWnd`  
 Fenêtre à masquage automatique à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE en cas de réussite, sinon FALSE.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setactiveingroup"></a>CMFCAutoHideBar::SetActiveInGroup  
 Marque une barre à masquage automatique comme active.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] BOOL`bActive`  
 TRUE pour définir l’état actif, sinon FALSE.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).  
  
##  <a name="setrecentvisiblestate"></a>CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bState`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="showautohidewindow"></a>CMFCAutoHideBar::ShowAutoHideWindow  
 Affiche la fenêtre à masquage automatique.  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] CDockablePane *`pAutoHideWnd`  
 [in] BOOL`bShow`  
 TRUE pour afficher la fenêtre.  
  
 [in] BOOL`bDelay`  
 Ce paramètre est ignoré.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE en cas de réussite, sinon FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="stretchpane"></a>CMFCAutoHideBar::StretchPane  
 Redimensionne la barre à masquage automatique à son état réduit pour faire tenir l’objet `CMFCAutoHideButton` .  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nLength`  
 La valeur n’est pas utilisée dans l’implémentation de base. Dans les implémentations dérivées, utilisez cette valeur pour indiquer la longueur du volet redimensionné.  
  
 [in] `bVert`  
 La valeur n’est pas utilisée dans l’implémentation de base. Dans les implémentations dérivées, utilisez `TRUE` pour gérer le cas où la barre de masquage automatique est réduite verticalement, et `FALSE` pour le cas où la barre de masquage automatique est réduite horizontalement.  
  
### <a name="return-value"></a>Valeur de retour  
 Taille résultante du volet redimensionné.  
  
### <a name="remarks"></a>Remarques  
 Les classes dérivées peuvent substituer cette méthode pour personnaliser le comportement.  
  
##  <a name="unsetautohidemode"></a>CMFCAutoHideBar::UnSetAutoHideMode  
 Désactive le mode de masquage automatique pour un groupe de barres avec masquage automatique.  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] pFirstBarInGroup  
 Pointeur vers la première barre à masquage automatique du groupe.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="updatevisiblestate"></a>CMFCAutoHideBar::UpdateVisibleState  
 Appelé par l’infrastructure quand de la barre à masquage automatique doit être redessinée.  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane (classe)](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite (classe)](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton (classe)](../../mfc/reference/cmfcautohidebutton-class.md)

