---
title: Classe de COleIPFrameWndEx | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx class
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5eec8e3a9cc4ad71a1ee3de9f6d5f25cffef1242
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx (classe)
La classe `COleIPFrameWndEx` implémente un conteneur OLE qui prend en charge MFC. Vous devez dériver la classe de fenêtre frame en place pour votre application à partir de la `COleIPFrameWndEx` (classe), au lieu de dériver de la [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||  
|[COleIPFrameWndEx::AddPane](#addpane)||  
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||  
|[COleIPFrameWndEx::DockPane](#dockpane)||  
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Ancre un volet à gauche d’un autre volet.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||  
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||  
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||  
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|Retourne un pointeur vers le menu contextuel actuellement affiché.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||  
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|Retourne l’ID de ressource de la fenêtre frame que vous avez spécifié quand la fenêtre a été chargée.|  
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||  
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||  
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||  
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|Retourne un pointeur vers l’objet de barre de menu attaché à la fenêtre frame.|  
|[COleIPFrameWndEx::GetPane](#getpane)||  
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|Retourne une liste d’objets de volet qui sont dans un état détachable.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Appelée par l’infrastructure avant l’affichage de l’info-bulle pour un bouton.|  
|[COleIPFrameWndEx::InsertPane](#insertpane)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Détermine si le pointeur vers l’objet de barre de menu n’est pas `NULL`.|  
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||  
|[COleIPFrameWndEx::LoadFrame](#loadframe)|(Substitue `COleIPFrameWnd::LoadFrame`.)|  
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||  
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Appelée par l’infrastructure quand un menu contextuel actif traite un message WM_DESTROY.|  
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|(Substitue `CFrameWnd::OnCmdMsg`.)|  
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Appelée par l’infrastructure quand l’image associée à un élément de menu est dessinée.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Appelé par l’infrastructure lorsqu’un [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)objet traite un message WM_PAINT.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Appelé par l’infrastructure lorsqu’un [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)objet traite WM_NCHITTEST message.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||  
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Appelez cette fonction membre pour définir la fenêtre frame principale de l’application dans et en dehors du mode Aperçu avant impression. (Substitue [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode).)|  
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||  
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||  
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Appelée par l’infrastructure quand un menu contextuel est activé.|  
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Appelée par l’infrastructure quand un menu avec une barre détachable est activé.|  
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||  
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|(Substitue `COleIPFrameWnd::PreTranslateMessage`.)|  
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|(Substitue `COleIPFrameWnd::RecalcLayout`.)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||  
|[COleIPFrameWndEx::SetDockState](#setdockstate)|Applique l’état d’ancrage spécifié aux volets qui appartiennent à la fenêtre frame.|  
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Modifie un objet de barre d’outils en recherchant des objets factices et en les remplaçant par les éléments définis par l’utilisateur spécifiés.|  
|[COleIPFrameWndEx::ShowPane](#showpane)||  
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|Appelée par l’infrastructure pour lancer l’application WinHelp ou l’aide contextuelle.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|Indique à l’infrastructure d’initialiser une plage d’ID de contrôle qui sont affectés aux barres d’outils définies par l’utilisateur.|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment créer une sous-classe d’une instance de la classe `COleIPFrameWndEx` et surcharger ses méthodes. L’exemple montre comment surcharger la méthode `OnDestory` , la méthode `RepositionFrame` , la méthode `RecalcLayout` et la méthode `CalcWindowRect` . Cet extrait de code fait partie de la [exemple du bloc-notes](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad n °&1;](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>COleIPFrameWndEx::AddDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="addpane"></a>COleIPFrameWndEx::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pControlBar`  
 [in] `bTail`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="adjustdockinglayout"></a>COleIPFrameWndEx::AdjustDockingLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hdwp`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="dockpane"></a>COleIPFrameWndEx::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 [in] `nDockBarID`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="dockpaneleftof"></a>COleIPFrameWndEx::DockPaneLeftOf  
 Ancre un volet à gauche d’un autre volet.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Pointeur vers le volet pour ancrer.  
  
 [in] `pLeftOf`  
 Pointeur vers le volet qui sert d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si l’opération a réussi. Sinon, retourne `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour ancrer plusieurs objets du volet dans un ordre prédéfini. Cette méthode est ancré le volet spécifié par `pBar` à gauche du volet spécifié par `pLeftOf`.  
  
##  <a name="enableautohidepanes"></a>COleIPFrameWndEx::EnableAutoHidePanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="enabledocking"></a>COleIPFrameWndEx::EnableDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="enablepanemenu"></a>COleIPFrameWndEx::EnablePaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly = FALSE,  
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 [in] `uiCustomizeCmd`  
 [in] `strCustomizeLabel`  
 [in] `uiViewToolbarsMenuEntryID`  
 [in] `bContextMenuShowsToolbarsOnly`  
 [in] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getactivepopup"></a>COleIPFrameWndEx::GetActivePopup  
 Retourne un pointeur vers la liste déroulante affichée.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la liste déroulante active ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour obtenir un pointeur vers le [CMFCPopupMenu classe](../../mfc/reference/cmfcpopupmenu-class.md) objet actuellement affiché.  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 Retourne l’ID de ressource de menu qui a été spécifiée lors du chargement du menu de la fenêtre frame.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’ID de ressource du menu, ou 0 si la fenêtre frame ne présente aucune barre de menus.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction pour récupérer l’ID de ressource qui a été spécifié lorsque la fenêtre frame chargé la ressource de menu en appelant `COleIPFrameWndEx::LoadFrame`.  
  
##  <a name="getdockframe"></a>COleIPFrameWndEx::GetDockFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getdockingmanager"></a>COleIPFrameWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getmainframe"></a>COleIPFrameWndEx::GetMainFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getmenubar"></a>COleIPFrameWndEx::GetMenuBar  
 Retourne un pointeur vers l’objet de barre de menu attaché à la fenêtre frame.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet de barre de menus.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet de récupérer un pointeur vers l’objet de barre de menus auquel appartient le `COleIPFrameWndEx` objet.  
  
##  <a name="getpane"></a>COleIPFrameWndEx::GetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="gettearoffbars"></a>COleIPFrameWndEx::GetTearOffBars  
 Retourne une liste d’objets de volet qui sont dans un état détachable.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à un `CObList` objet qui contient une collection de pointeurs vers les [CBasePane classe](../../mfc/reference/cbasepane-class.md)-objets dérivés.  
  
### <a name="remarks"></a>Notes  
 Le `COleIPFrameWndEx` objet maintient la collection des menus volants comme une liste de [CBasePane classe](../../mfc/reference/cbasepane-class.md)-objets dérivés. Utilisez cette méthode pour récupérer une référence à cette liste.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 Appelée par l’infrastructure avant l’affichage de l’info-bulle pour un bouton.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pButton`  
 Pointeur sur le bouton.  
  
 [in] `strTTText`  
 Pointeur vers le texte d’info-bulle.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut retourne 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour personnaliser l’affichage des info-bulles des boutons de barre d’outils.  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 Spécifie une plage d’ID qui affecte de l’infrastructure pour les barres d’outils définis par l’utilisateur.  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszRegEntry`  
 L’entrée de Registre dans laquelle la bibliothèque stocke les paramètres utilisateur.  
  
 [in] `uiUserToolbarFirst`  
 ID de contrôle attribué à la première barre d’outils définis par l’utilisateur.  
  
 [in] `uiUserToolbarLast`  
 ID de contrôle attribué à la dernière barre d’outils définis par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour initialiser une plage d’ID de contrôle pour l’attribution aux barres d’outils que les utilisateurs définir dynamiquement. Les paramètres `uiUserToolbarFirst` et `uiUserToolbarLast` définissent une plage d’ID de contrôle de barre d’outils autorisées. Pour désactiver la création de barres d’outils de défini par l’utilisateur, définissez `uiUserToolbarFirst` ou `uiUserToolbarLast` -1.  
  
##  <a name="insertpane"></a>COleIPFrameWndEx::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pControlBar`  
 [in] `pTarget`  
 [in] `bAfter`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ismenubaravailable"></a>COleIPFrameWndEx::IsMenuBarAvailable  
 Détermine si le pointeur vers l’objet de barre de menu n’est pas`NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur retourne un zéro si la fenêtre frame possède une barre de menus ; Sinon, retourne 0.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour déterminer si la fenêtre frame gère non `NULL` pointeur à son objet de barre de menus.  
  
##  <a name="ispointneardocksite"></a>COleIPFrameWndEx::IsPointNearDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 [in] `dwBarAlignment`  
 [in] `bOuterEdge`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="loadframe"></a>COleIPFrameWndEx::LoadFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIDResource`  
 [in] `dwDefaultStyle`  
 [in] `pParentWnd`  
 [in] `pContext`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onclosedockingpane"></a>COleIPFrameWndEx::OnCloseDockingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CDockablePane*`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="oncloseminiframe"></a>COleIPFrameWndEx::OnCloseMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onclosepopupmenu"></a>COleIPFrameWndEx::OnClosePopupMenu  
 Appelé par l’infrastructure lorsqu’un menu contextuel actif traite un `WM_DESTROY` message.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMenuPopup`  
 Pointeur vers l’objet menu contextuel.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour recevoir des notifications à partir de `CMFCPopupMenu` lorsqu’ils traitent les objets `WM_DESTROY` messages.  
  
##  <a name="oncmdmsg"></a>COleIPFrameWndEx::OnCmdMsg  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 [in] `nCode`  
 [in] `pExtra`  
 [in] `pHandlerInfo`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="ondrawmenuimage"></a>COleIPFrameWndEx::OnDrawMenuImage  
 Appelé par l’infrastructure lorsque l’image associée à un élément de menu est dessiné.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique.  
  
 [in] `pMenuButton`  
 Pointeur sur le bouton de menu.  
  
 [in] `rectImage`  
 L’image associée à l’élément de menu.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut ne fait rien et retourne 0.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode si vous souhaitez personnaliser l’image pour les éléments de menu qui appartiennent à la barre de menus détenue par le `COleIPFrameWndEx`-objet dérivé.  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 Appelé par l’infrastructure lorsqu’un [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)de l’objet processus une `WM_PAINT` message.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique.  
  
 [in] `pMenu`  
 Pointeur vers l’objet menu contextuel.  
  
 [in] `rectLogo`  
 Pointeur vers le logo à afficher.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour afficher un logo dans le menu contextuel associé à la barre de menus détenue par le `COleIPFrameWndEx`-objet dérivé. L'implémentation par défaut n'exécute aucune opération.  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 Appelé par l’infrastructure lorsqu’un [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)de l’objet processus une `WM_NCHITTEST` message.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] pButton  
 Pointeur vers un bouton de menu.  
  
 [out] pTI  
 Pointeur désignant une structure `TOOLINFO`.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut ne fait rien et retourne 0. Votre implémentation doit retourner une valeur différente de zéro si elle remplit la `pTI` paramètre.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour fournir des informations d’info-bulle sur un élément de menu spécifique.  
  
##  <a name="onmoveminiframe"></a>COleIPFrameWndEx::OnMoveMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFrame`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onsetpreviewmode"></a>COleIPFrameWndEx::OnSetPreviewMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bPreview`  
 [in] `pState`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onshowcustomizepane"></a>COleIPFrameWndEx::OnShowCustomizePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMenuPane`  
 [in] `uiToolbarID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onshowpanes"></a>COleIPFrameWndEx::OnShowPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onshowpopupmenu"></a>COleIPFrameWndEx::OnShowPopupMenu  
 Appelé par l’infrastructure lorsqu’un menu contextuel s’affiche.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Paramètres  
 `[in] pMenuPopup`  
 Pointeur vers le menu contextuel s’affiche.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut ne fait rien et retourne une valeur différente de zéro. Votre implémentation doit retourner `FALSE` si le menu contextuel ne peut pas être affiché.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour personnaliser l’affichage d’un menu contextuel. Par exemple, vous pourrez modifier les boutons de menu pour les boutons de menu couleur ou initialiser détachable barres.  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 Appelé par l’infrastructure lorsque l’utilisateur sélectionne un menu qui possède une barre détachables.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMenuPopup`  
 Pointeur vers le menu contextuel sélectionné par l’utilisateur.  
  
 [in] `pBar`  
 Pointeur vers le volet qui héberge le menu.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si vous souhaitez que l’infrastructure pour activer le menu contextuel ; dans le cas contraire `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction si vous souhaitez personnaliser l’installation de la barre à détacher.  
  
##  <a name="panefrompoint"></a>COleIPFrameWndEx::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 [in] `nSensitivity`  
 [in] `bExactBar`  
 [in] `pRTCBarType`  
 [in] `dwAlignment`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="pretranslatemessage"></a>COleIPFrameWndEx::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMsg`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="recalclayout"></a>COleIPFrameWndEx::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bNotify`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="removepanefromdockmanager"></a>COleIPFrameWndEx::RemovePaneFromDockManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pControlBar`  
 [in] `bDestroy`  
 [in] `bAdjustLayout`  
 [in] `bAutoHide`  
 [in] `pBarReplacement`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setdockstate"></a>COleIPFrameWndEx::SetDockState  
 S’applique à l’état d’ancrage spécifié dans des volets qui appartiennent à la fenêtre frame.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `state`  
 Spécifie l’état d’ancrage.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet de spécifier un nouvel état d’ancrage pour les volets qui appartiennent à la `COleIPFrameWndEx` objet.  
  
##  <a name="setuptoolbarmenu"></a>COleIPFrameWndEx::SetupToolbarMenu  
 Modifie un objet de barre d’outils en recherchant des objets factices et en les remplaçant par les éléments définis par l’utilisateur spécifiés.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `menu`  
 Une référence à un [CMenu](../../mfc/reference/cmenu-class.md) objet à modifier.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 Spécifie la première commande défini par l’utilisateur.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Spécifie la dernière commande défini par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="showpane"></a>COleIPFrameWndEx::ShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="winhelpa"></a>COleIPFrameWndEx::WinHelpA  
 Appelée par l’infrastructure pour lancer l’application WinHelp ou l’aide contextuelle.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] dwData  
 Spécifie les données requises pour le type d’aide spécifié par `nCmd`.  
  
 [in] `nCmd`  
 Spécifie le type d’aide demandée. Pour obtenir la liste des valeurs possibles et savoir comment elles affectent le paramètre `dwData` , consultez la [fonction WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) dans le Kit de développement logiciel (SDK) Windows.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx (classe)](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)

