---
title: Classe de CPaneDivider | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
dev_langs:
- C++
helpviewer_keywords:
- CPaneDivider class
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
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
ms.openlocfilehash: b1c6b8b608deb2c81a2a646345ee4020c27820e7
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedivider-class"></a>CPaneDivider (classe)
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 La `CPaneDivider` classe divise deux volets, divise deux groupes de volets ou sépare un groupe de volets de la zone cliente de la fenêtre frame principale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaneDivider::CPaneDivider](#cpanedivider)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||  
|[CPaneDivider::AddPane](#addpane)||  
|[CPaneDivider::AddRecentPane](#addrecentpane)||  
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||  
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(Substitue [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CPaneDivider::CheckVisibility](#checkvisibility)||  
|[CPaneDivider::CreateEx](#createex)|(Substitue [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|  
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Substitue [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||  
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||  
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||  
|[CPaneDivider::GetFirstPane](#getfirstpane)||  
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||  
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||  
|[CPaneDivider::GetWidth](#getwidth)||  
|[CPaneDivider::Init](#init)||  
|[CPaneDivider::InsertPane](#insertpane)||  
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(Substitue [CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|  
|[CPaneDivider::IsDefault](#isdefault)||  
|[CPaneDivider::IsHorizontal](#ishorizontal)|(Substitue [CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|  
|[CPaneDivider::Move](#move)||  
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||  
|[CPaneDivider::OnShowPane](#onshowpane)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneDivider::RemovePane](#removepane)||  
|[CPaneDivider::ReplacePane](#replacepane)||  
|[CPaneDivider::RepositionPanes](#repositionpanes)||  
|[CPaneDivider::Serialize](#serialize)|(Substitue `CBasePane::Serialize`.)|  
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||  
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||  
|[CPaneDivider::ShowWindow](#showwindow)||  
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaneDivider::GetPanes](#getpanes)|Retourne la liste de volets qui se trouvent dans le [CPaneContainer classe](../../mfc/reference/cpanecontainer-class.md). Cette méthode doit être appelée uniquement pour les séparateurs de volets par défaut.|  
|[CPaneDivider::GetPaneDividers](#getpanedividers)|Retourne la liste de diviseurs de volet qui résident dans le [CPaneContainer classe](../../mfc/reference/cpanecontainer-class.md). Cette méthode doit être appelée uniquement pour les séparateurs de volets par défaut.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|Spécifie la largeur par défaut en pixels de tous les séparateurs de volets de l’application.|  
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|Contient un pointeur vers les informations de classe d’exécution sur un `CPaneDivider`-objet dérivé.|  
  
## <a name="remarks"></a>Notes  
 L’infrastructure crée `CPaneDivider` objets automatiquement lorsqu’un volet est ancré.  
  
 Il existe deux types de diviseurs de volet :  
  
-   un diviseur de volet par défaut est créé lorsqu’un groupe de volets est ancré à un côté de la fenêtre frame principale. Le diviseur de volet par défaut conserve un pointeur vers le [CPaneContainerManager classe](../../mfc/reference/cpanecontainermanager-class.md) et redirige la plupart des opérations sur le groupe de volets (telles que le redimensionnement d’un volet ou une autre station d’accueil volet ou un conteneur) dans le Gestionnaire de conteneur. Chaque volet d’ancrage conserve un pointeur vers son diviseur de volet par défaut.  
  
-   Une barre de séparation régulière divise simplement deux volets dans un conteneur. Pour plus d’informations, consultez [CPaneContainer classe](../../mfc/reference/cpanecontainer-class.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment obtenir un objet `CPaneDivider` à partir d'un objet `CWorkspaceBar`. Cet extrait de code fait partie de la [exemple de démonstration des onglets MDI](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo n °&5;](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxPaneDivider.h  
  
##  <a name="setautohidemode"></a>CPaneDivider::SetAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAutoHideMode(BOOL bMode);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bMode`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setpanecontainermanager"></a>CPaneDivider::SetPaneContainerManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPaneContainerManager(CPaneContainerManager* p);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `p`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="addpane"></a>CPaneDivider::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="addpanecontainer"></a>CPaneDivider::AddPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,  
    BOOL bOuterEdge);

 
virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,  
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `barContainerManager`  
 [in] `bOuterEdge`  
 [in] `pTargetBar`  
 [in] `dwAlignment`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="addrecentpane"></a>CPaneDivider::AddRecentPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="calcexpecteddockedrect"></a>CPaneDivider::CalcExpectedDockedRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndToDock`  
 [in] `ptMouse`  
 [in] `rectResult`  
 [in] `bDrawTab`  
 [in] `ppTargetBar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="calcfixedlayout"></a>CPaneDivider::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
  
##  <a name="checkvisibility"></a>CPaneDivider::CheckVisibility  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CheckVisibility();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="cpanedivider"></a>CPaneDivider::CPaneDivider  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneDivider();

 
CPaneDivider(
    BOOL bDefaultSlider,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDefaultSlider`  
 [in] `pParent`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="createex"></a>CPaneDivider::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwStyleEx`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `nID`  
 [in] `pContext`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="doesallowdyninsertbefore"></a>CPaneDivider::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="doescontainfloatingpane"></a>CPaneDivider::DoesContainFloatingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="findpanecontainer"></a>CPaneDivider::FindPaneContainer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 [in] `bLeftBar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="findtabbedpane"></a>CPaneDivider::FindTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getdefaultwidth"></a>CPaneDivider::GetDefaultWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static int __stdcall GetDefaultWidth();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getfirstpane"></a>CPaneDivider::GetFirstPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpanedividers"></a>CPaneDivider::GetPaneDividers  
 Retourne la liste de diviseurs de volet qui résident dans le [CPaneContainer classe](../../mfc/reference/cpanecontainer-class.md). Cette méthode doit être appelée uniquement pour les séparateurs de volets par défaut.  
  
```  
void GetPaneDividers(CObList& lstSliders);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `lstSliders`  
 Contient la liste de diviseurs de volet qui résident dans le conteneur de volet.  
  
### <a name="remarks"></a>Notes  
 Cette méthode doit être appelée pour seulement les séparateurs de volets par défaut. Un diviseur de volet par défaut est un séparateur qui redimensionne le conteneur de volet entière.  
  
##  <a name="getpanedividerstyle"></a>CPaneDivider::GetPaneDividerStyle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
DWORD GetPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getpanes"></a>CPaneDivider::GetPanes  
 Retourne la liste de volets qui se trouvent dans le [CPaneContainer classe](../../mfc/reference/cpanecontainer-class.md). Cette méthode doit être appelée uniquement pour récupérer des diviseurs de volet par défaut.  
  
```  
void GetPanes(CObList& lstBars);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `lstBars`  
 Contient la liste de volets qui se trouvent dans le conteneur de volet.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée pour seulement les séparateurs de volets par défaut. Un diviseur de volet par défaut est un séparateur qui redimensionne le conteneur de volet entière.  
  
##  <a name="getrootcontainerrect"></a>CPaneDivider::GetRootContainerRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetRootContainerRect();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getwidth"></a>CPaneDivider::GetWidth  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetWidth() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="init"></a>CPaneDivider::Init  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Init(
    BOOL bDefaultSlider = FALSE,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDefaultSlider`  
 [in] `pParent`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="insertpane"></a>CPaneDivider::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,  
    CDockablePane* pTargetBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBarToInsert`  
 [in] `pTargetBar`  
 [in] `dwAlignment`  
 [in] `lpRect`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="isautohidemode"></a>CPaneDivider::IsAutoHideMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="isdefault"></a>CPaneDivider::IsDefault  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDefault() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="ishorizontal"></a>CPaneDivider::IsHorizontal  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="m_ndefaultwidth"></a>CPaneDivider::m_nDefaultWidth  
 Spécifie la largeur par défaut, en pixels, de tous les séparateurs de volets de l’application.  
  
```  
AFX_IMPORT_DATA static int m_nDefaultWidth;  
```  
  
##  <a name="move"></a>CPaneDivider::Move  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Move(
    CPoint& ptOffset,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ptOffset`  
 [in] `bAdjustLayout`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_psliderrtc"></a>CPaneDivider::m_pSliderRTC  
 Contient un pointeur vers les informations de classe d’exécution sur un `CPaneDivider`-objet dérivé.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez cette variable membre si vous créez un diviseur de volet personnalisé. Ainsi, le framework pour créer votre barre de séparation lorsque le volet est dessiné.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment définir le `m_pSliderRTC` variable membre :  
  
```  
class CMySplitter : public CPaneDivider  
{  
...  
};  
 
CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```  
  
##  <a name="notifyaboutrelease"></a>CPaneDivider::NotifyAboutRelease  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void NotifyAboutRelease();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="onshowpane"></a>CPaneDivider::OnShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 [in] `bShow`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="releaseemptypanecontainers"></a>CPaneDivider::ReleaseEmptyPaneContainers  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="removepane"></a>CPaneDivider::RemovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="replacepane"></a>CPaneDivider::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,  
    CDockablePane* pBarToReplaceWith);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBarToReplace`  
 [in] `pBarToReplaceWith`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="repositionpanes"></a>CPaneDivider::RepositionPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RepositionPanes(
    CRect& rectNew,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rectNew`  
 [in] `hdwp`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="serialize"></a>CPaneDivider::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="showwindow"></a>CPaneDivider::ShowWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nCmdShow`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="storerecentdocksiteinfo"></a>CPaneDivider::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="storerecenttabrelatedinfo"></a>CPaneDivider::StoreRecentTabRelatedInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockingBar`  
 [in] `pTabbedBar`  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager (classe)](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer (classe)](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager (classe)](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane (classe)](../../mfc/reference/cbasepane-class.md)

