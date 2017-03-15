---
title: Classe de CMultiPaneFrameWnd | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPaneFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- CMultiPaneFrameWnd class
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
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
ms.openlocfilehash: 4332533097b6e2463c21065ef361969397cacf5e
ms.lasthandoff: 02/24/2017

---
# <a name="cmultipaneframewnd-class"></a>CMultiPaneFrameWnd (classe)
Le `CMultiPaneFrameWnd` étend la classe [CPaneFrameWnd classe](../../mfc/reference/cpaneframewnd-class.md). Elle peut prendre en charge plusieurs volets. Au lieu d’un seul handle incorporé à une barre de contrôle `CMultiPaneFrameWnd` contient un [CPaneContainerManager classe](../../mfc/reference/cpanecontainermanager-class.md) objet qui permet à l’utilisateur d’ancrer un `CMultiPaneFrameWnd` à un autre et dynamiquement créer plusieurs fenêtres flottantes avec onglets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMultiPaneFrameWnd::AddPane](#addpane)|Ajoute un volet. (Substitue [CPaneFrameWnd::AddPane](../../mfc/reference/cpaneframewnd-class.md#addpane).)|  
|[CMultiPaneFrameWnd::AddRecentPane](#addrecentpane)||  
|[CMultiPaneFrameWnd::AdjustLayout](#adjustlayout)|Ajuste la disposition de la fenêtre mini-frame. (Substitue [CPaneFrameWnd::AdjustLayout](../../mfc/reference/cpaneframewnd-class.md#adjustlayout).)|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)|(Substitue [CPaneFrameWnd::AdjustPaneFrames](../../mfc/reference/cpaneframewnd-class.md#adjustpaneframes).)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Calcule le rectangle attendu d’une fenêtre ancrée. (Substitue [CPaneFrameWnd::CalcExpectedDockedRect](../../mfc/reference/cpaneframewnd-class.md#calcexpecteddockedrect).)|  
|[CMultiPaneFrameWnd::CanBeAttached](#canbeattached)|Détermine si le volet actif pouvez ancrer à un autre volet ou une fenêtre frame. (Substitue [CPaneFrameWnd::CanBeAttached](../../mfc/reference/cpaneframewnd-class.md#canbeattached).)|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Détermine si la fenêtre mini-frame pouvez ancrer un volet. (Substitue [CPaneFrameWnd::CanBeDockedToPane](../../mfc/reference/cpaneframewnd-class.md#canbedockedtopane).)|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)|(Substitue [CPaneFrameWnd::CheckGripperVisibility](../../mfc/reference/cpaneframewnd-class.md#checkgrippervisibility).)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](#closeminiframe)|(Substitue `CPaneFrameWnd::CloseMiniFrame`.)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Convertit le volet en document à onglets. (Substitue [CPaneFrameWnd::ConvertToTabbedDocument](../../mfc/reference/cpaneframewnd-class.md#converttotabbeddocument).)|  
|[CMultiPaneFrameWnd::DockFrame](#dockframe)||  
|[CMultiPaneFrameWnd::DockPane](#dockpane)|Ancre le volet. (Substitue [CPaneFrameWnd::DockPane](../../mfc/reference/cpaneframewnd-class.md#dockpane).)|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](#dockrecentpanetomainframe)||  
|[CMultiPaneFrameWnd::GetCaptionText](#getcaptiontext)|Retourne le texte de légende. (Substitue [CPaneFrameWnd::GetCaptionText](../../mfc/reference/cpaneframewnd-class.md#getcaptiontext).)|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](#getpanecontainermanager)|Retourne une référence à l’objet de gestionnaire de conteneur interne.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Retourne le premier volet visible contenu dans une fenêtre mini-frame. (Substitue [CPaneFrameWnd::GetFirstVisiblePane](../../mfc/reference/cpaneframewnd-class.md#getfirstvisiblepane).)|  
|[CMultiPaneFrameWnd::GetPane](#getpane)|Retourne un volet contenu dans la fenêtre mini-frame. (Substitue [CPaneFrameWnd::GetPane](../../mfc/reference/cpaneframewnd-class.md#getpane).)|  
|[CMultiPaneFrameWnd::GetPaneCount](#getpanecount)|Retourne le nombre de volets contenus dans une fenêtre mini-frame. (Substitue [CPaneFrameWnd::GetPaneCount](../../mfc/reference/cpaneframewnd-class.md#getpanecount).)|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Retourne le nombre de volets visibles contenus dans une fenêtre mini-frame. (Substitue [CPaneFrameWnd::GetVisiblePaneCount](../../mfc/reference/cpaneframewnd-class.md#getvisiblepanecount).)|  
|[CMultiPaneFrameWnd::InsertPane](#insertpane)||  
|[CMultiPaneFrameWnd::LoadState](#loadstate)|Charge l'état du volet à partir du Registre. (Substitue [CPaneFrameWnd::LoadState](../../mfc/reference/cpaneframewnd-class.md#loadstate).)|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Ancre la fenêtre mini-frame à sa dernière position. (Substitue [CPaneFrameWnd::OnDockToRecentPos](../../mfc/reference/cpaneframewnd-class.md#ondocktorecentpos).)|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Arrête le minuteur d'affichage. (Substitue [CPaneFrameWnd::OnKillRollUpTimer](../../mfc/reference/cpaneframewnd-class.md#onkillrolluptimer).)|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Ajuste la disposition d’un volet dans une fenêtre mini-frame. (Substitue [CPaneFrameWnd::OnPaneRecalcLayout](../../mfc/reference/cpaneframewnd-class.md#onpanerecalclayout).)|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Définit le minuteur d'affichage. (Substitue [CPaneFrameWnd::OnSetRollUpTimer](../../mfc/reference/cpaneframewnd-class.md#onsetrolluptimer).)|  
|[CMultiPaneFrameWnd::OnShowPane](#onshowpane)|Appelé par l'infrastructure quand un volet de la fenêtre mini-frame est masqué ou affiché. (Substitue [CPaneFrameWnd::OnShowPane](../../mfc/reference/cpaneframewnd-class.md#onshowpane).)|  
|[CMultiPaneFrameWnd::PaneFromPoint](#panefrompoint)|Retourne un volet s'il contient un point fourni par l'utilisateur à l'intérieur d'une fenêtre mini-frame. (Substitue [CPaneFrameWnd::PaneFromPoint](../../mfc/reference/cpaneframewnd-class.md#panefrompoint).)|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Appelé par l'infrastructure pour supprimer les volets non valides. (Substitue [CPaneFrameWnd::RemoveNonValidPanes](../../mfc/reference/cpaneframewnd-class.md#removenonvalidpanes).)|  
|[CMultiPaneFrameWnd::RemovePane](#removepane)|Supprime un volet de la fenêtre mini-frame. (Substitue [CPaneFrameWnd::RemovePane](../../mfc/reference/cpaneframewnd-class.md#removepane).)|  
|[CMultiPaneFrameWnd::ReplacePane](#replacepane)|Remplace un volet par un autre. (Substitue [CPaneFrameWnd::ReplacePane](../../mfc/reference/cpaneframewnd-class.md#replacepane).)|  
|[CMultiPaneFrameWnd::SaveState](#savestate)|Enregistre l'état du volet dans le Registre. (Substitue [CPaneFrameWnd::SaveState](../../mfc/reference/cpaneframewnd-class.md#savestate).)|  
|[CMultiPaneFrameWnd::Serialize](#serialize)|(Substitue `CPaneFrameWnd::Serialize`.)|  
|[CMultiPaneFrameWnd::SetDockState](#setdockstate)|Définit l'état d'ancrage. (Substitue [CPaneFrameWnd::SetDockState](../../mfc/reference/cpaneframewnd-class.md#setdockstate).)|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](#setlastfocusedpane)||  
|[CMultiPaneFrameWnd::SetPreDockState](#setpredockstate)|Définit l’état predocking. (Substitue [CPaneFrameWnd::SetPreDockState](../../mfc/reference/cpaneframewnd-class.md#setpredockstate).)|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)|(Substitue [CPaneFrameWnd::StoreRecentDockSiteInfo](../../mfc/reference/cpaneframewnd-class.md#storerecentdocksiteinfo).)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)|(Substitue [CPaneFrameWnd::StoreRecentTabRelatedInfo](../../mfc/reference/cpaneframewnd-class.md#storerecenttabrelatedinfo).)|  
  
## <a name="remarks"></a>Remarques  
 La plupart des méthodes de cette classe de substituer les méthodes dans le [CPaneFrameWnd classe](../../mfc/reference/cpaneframewnd-class.md) classe.  
  
 Si un volet utilise le `AFX_CBRS_AUTO_ROLLUP` style et l’utilisateur ce volet est ancré à une fenêtre frame de plusieurs volets, l’utilisateur peut restaurer la fenêtre indépendamment des paramètres de style des autres volets ancrés.  
  
 Le framework crée automatiquement une `CMultiPaneFrameWnd` objet lorsque l’utilisateur flotte un volet qui utilise le `CBRS_FLOAT_MULTI` style.  
  
 Pour plus d’informations sur la dérivation d’une classe à partir de la `CPaneFrameWnd` de classe et la création dynamique, consultez [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment récupérer un pointeur vers un `CMultiPaneFrameWnd` objet. Cet extrait de code fait partie de la [exemple de définir la taille du volet](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize n °&4;](../../mfc/reference/codesnippet/cpp/cmultipaneframewnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxMultiPaneFrameWnd.h  
  
##  <a name="a-nameaddpanea--cmultipaneframewndaddpane"></a><a name="addpane"></a>CMultiPaneFrameWnd::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddrecentpanea--cmultipaneframewndaddrecentpane"></a><a name="addrecentpane"></a>CMultiPaneFrameWnd::AddRecentPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameadjustlayouta--cmultipaneframewndadjustlayout"></a><a name="adjustlayout"></a>CMultiPaneFrameWnd::AdjustLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameadjustpaneframesa--cmultipaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>CMultiPaneFrameWnd::AdjustPaneFrames  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecalcexpecteddockedrecta--cmultipaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CMultiPaneFrameWnd::CalcExpectedDockedRect  
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
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecanbeattacheda--cmultipaneframewndcanbeattached"></a><a name="canbeattached"></a>CMultiPaneFrameWnd::CanBeAttached  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecanbedockedtopanea--cmultipaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>CMultiPaneFrameWnd::CanBeDockedToPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockingBar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecheckgrippervisibilitya--cmultipaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CMultiPaneFrameWnd::CheckGripperVisibility  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecloseminiframea--cmultipaneframewndcloseminiframe"></a><a name="closeminiframe"></a>CMultiPaneFrameWnd::CloseMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CloseMiniFrame();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameconverttotabbeddocumenta--cmultipaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CMultiPaneFrameWnd::ConvertToTabbedDocument  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namedockframea--cmultipaneframewnddockframe"></a><a name="dockframe"></a>CMultiPaneFrameWnd::DockFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DockFrame(
    CPaneFrameWnd* pDockedFrame,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockedFrame`  
 [in] `dockMethod`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedockpanea--cmultipaneframewnddockpane"></a><a name="dockpane"></a>CMultiPaneFrameWnd::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DockPane(CDockablePane* pDockedBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockedBar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namedockrecentpanetomainframea--cmultipaneframewnddockrecentpanetomainframe"></a><a name="dockrecentpanetomainframe"></a>CMultiPaneFrameWnd::DockRecentPaneToMainFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DockRecentPaneToMainFrame(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetcaptiontexta--cmultipaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>CMultiPaneFrameWnd::GetCaptionText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetfirstvisiblepanea--cmultipaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CMultiPaneFrameWnd::GetFirstVisiblePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetpanea--cmultipaneframewndgetpane"></a><a name="getpane"></a>CMultiPaneFrameWnd::GetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetpanecontainermanagera--cmultipaneframewndgetpanecontainermanager"></a><a name="getpanecontainermanager"></a>CMultiPaneFrameWnd::GetPaneContainerManager  
 Retourne une référence à l’objet de gestionnaire de conteneur interne.  
  
```  
CPaneContainerManager& GetPaneContainerManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’objet de gestionnaire de conteneur interne.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode peut être utilisée pour accéder aux interne [CPaneContainerManager classe](../../mfc/reference/cpanecontainermanager-class.md) objet.  
  
##  <a name="a-namegetpanecounta--cmultipaneframewndgetpanecount"></a><a name="getpanecount"></a>CMultiPaneFrameWnd::GetPaneCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetvisiblepanecounta--cmultipaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CMultiPaneFrameWnd::GetVisiblePaneCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameinsertpanea--cmultipaneframewndinsertpane"></a><a name="insertpane"></a>CMultiPaneFrameWnd::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pControlBar`  
 [in] `pTarget`  
 [in] `bAfter`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameloadstatea--cmultipaneframewndloadstate"></a><a name="loadstate"></a>CMultiPaneFrameWnd::LoadState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 [in] `uiID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondocktorecentposa--cmultipaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>CMultiPaneFrameWnd::OnDockToRecentPos  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDockToRecentPos();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonkillrolluptimera--cmultipaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>CMultiPaneFrameWnd::OnKillRollUpTimer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnKillRollUpTimer();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonpanerecalclayouta--cmultipaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>CMultiPaneFrameWnd::OnPaneRecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonsetrolluptimera--cmultipaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CMultiPaneFrameWnd::OnSetRollUpTimer  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSetRollUpTimer();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonshowpanea--cmultipaneframewndonshowpane"></a><a name="onshowpane"></a>CMultiPaneFrameWnd::OnShowPane  
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
  
##  <a name="a-namepanefrompointa--cmultipaneframewndpanefrompoint"></a><a name="panefrompoint"></a>CMultiPaneFrameWnd::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 [in] `nSensitivity`  
 [in] `bCheckVisibility`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameremovenonvalidpanesa--cmultipaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CMultiPaneFrameWnd::RemoveNonValidPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameremovepanea--cmultipaneframewndremovepane"></a><a name="removepane"></a>CMultiPaneFrameWnd::RemovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePane(
    CBasePane* pBar,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 [in] `bDestroy`  
 [in] `bNoDelayedDestroy`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namereplacepanea--cmultipaneframewndreplacepane"></a><a name="replacepane"></a>CMultiPaneFrameWnd::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBarOrg`  
 [in] `pBarReplaceWith`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesavestatea--cmultipaneframewndsavestate"></a><a name="savestate"></a>CMultiPaneFrameWnd::SaveState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 [in] `uiID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameserializea--cmultipaneframewndserialize"></a><a name="serialize"></a>CMultiPaneFrameWnd::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ar`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetdockstatea--cmultipaneframewndsetdockstate"></a><a name="setdockstate"></a>CMultiPaneFrameWnd::SetDockState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDockManager`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetlastfocusedpanea--cmultipaneframewndsetlastfocusedpane"></a><a name="setlastfocusedpane"></a>CMultiPaneFrameWnd::SetLastFocusedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLastFocusedPane(HWND hwnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hwnd`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetpredockstatea--cmultipaneframewndsetpredockstate"></a><a name="setpredockstate"></a>CMultiPaneFrameWnd::SetPreDockState  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `preDockState`  
 [in] `pBarToDock`  
 [in] `dockMethod`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namestorerecentdocksiteinfoa--cmultipaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CMultiPaneFrameWnd::StoreRecentDockSiteInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namestorerecenttabrelatedinfoa--cmultipaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CMultiPaneFrameWnd::StoreRecentTabRelatedInfo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void StoreRecentTabRelatedInfo(
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
 [CPaneFrameWnd (classe)](../../mfc/reference/cpaneframewnd-class.md)

