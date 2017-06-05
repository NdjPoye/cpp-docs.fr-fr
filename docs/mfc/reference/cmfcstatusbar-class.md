---
title: Classe de CMFCStatusBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
dev_langs:
- C++
helpviewer_keywords:
- CMFCStatusBar class
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 20881637d74bafffbcf2e0c3dcd1cc98e173aa07
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcstatusbar-class"></a>Classe de CMFCStatusBar
Le `CMFCStatusBar` classe implémente une barre d’état semblable à la `CStatusBar` classe. Toutefois, la classe `CMFCStatusBar` a des fonctionnalités que n'offre pas la classe `CStatusBar` , telles que la capacité à afficher des images, des animations et des barres de progression et la possibilité de répondre aux doubles-clics de souris. 

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Substitue [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||  
|[CMFCStatusBar::Create](#create)|Crée une barre de contrôle et l’attache à la [CPane](../../mfc/reference/cpane-class.md) objet. (Substitue [CPane::Create](../../mfc/reference/cpane-class.md#create).)|  
|[CMFCStatusBar::CreateEx](#createex)|Crée une barre de contrôle et l’attache à la [CPane](../../mfc/reference/cpane-class.md) objet. (Substitue [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Détermine si un autre volet peut être dynamiquement inséré dans ce volet et le frame parent. (Substitue [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Active ou désactive la gestion de la souris double-clique sur la barre d’état.|  
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Affiche une barre de progression dans le volet spécifié.|  
|[CMFCStatusBar::GetCount](#getcount)|Retourne le nombre de volets dans la barre d’état.|  
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||  
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCStatusBar::GetItemID](#getitemid)||  
|[CMFCStatusBar::GetItemRect](#getitemrect)||  
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||  
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||  
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Retourne le style du volet. (Substitue [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|  
|[CMFCStatusBar::GetPaneText](#getpanetext)||  
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Retourne la largeur, en pixels, du volet de la barre d’état spécifié.|  
|[CMFCStatusBar::GetTipText](#gettiptext)|Retourne le texte info-bulle pour le volet de la barre d’état spécifié.|  
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Invalide le volet spécifié et son contenu pour redessiner.|  
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Appelé par l’infrastructure avant la création de la fenêtre Windows associée à ce `CWnd` objet. (Substitue [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|  
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||  
|[CMFCStatusBar::SetIndicators](#setindicators)||  
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Assigne une animation dans le volet spécifié.|  
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Définit la couleur d’arrière-plan du volet de la barre d’état spécifié.|  
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Définit l’icône d’indicateur du volet de la barre d’état spécifié.|  
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||  
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Définit la progression actuelle de la barre de progression pour le volet de la barre d’état spécifié.|  
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Définit le style du volet. (Substitue [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|  
|[CMFCStatusBar::SetPaneText](#setpanetext)||  
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Définit la couleur du texte pour le volet de la barre d’état spécifié.|  
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Définit la largeur en pixels du volet de la barre d’état spécifié.|  
|[CMFCStatusBar::SetTipText](#settiptext)|Définit le texte info-bulle pour le volet de la barre d’état spécifié.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Appelé par l’infrastructure lorsqu’il redessine le volet de la barre d’état.|  
  
## <a name="remarks"></a>Notes  
 Le diagramme suivant illustre un chiffre de la barre d’état [exemple de démonstration de barre d’état](../../visual-cpp-samples.md) application.  
  
 ![Exemple de CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "cmfcstatusbar")  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre les variables locales que l’application utilise pour appeler les différentes méthodes la `CMFCStatusBar` classe. Ces variables sont déclarées dans StatusBarDemoView.h. Le frame principal est déclaré dans MainFrm.h, le document est déclaré dans StatusBarDemoDoc.h et la vue est déclarée dans StatusBarDemoView.h. Cet extrait de code fait partie de la [exemple de démonstration de barre d’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#9;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment obtenir une référence à `CMFCStatusBar` objet en introduisant le `GetStatusBar` méthode MainFrm.h, puis en appelant cette méthode à partir de la `GetStatusBar` méthode dans StatusBarDemoView.h. Cet extrait de code fait partie de la [exemple de démonstration de barre d’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#7;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&8;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment appeler des méthodes la `CMFCStatusBar` classe dans StatusBarDemoView.cpp. Les constantes sont déclarées dans MainFrm.h. L’exemple montre comment définir l’icône, définir le texte d’info-bulle du volet de barre d’état, afficher une barre de progression dans le volet spécifié, attribuer une animation dans le volet spécifié, définir le texte et la largeur du volet de barre d’état et l’indicateur de progression de la barre de progression pour le volet de barre d’état. Cet extrait de code fait partie de la [exemple de démonstration de barre d’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo n °&6;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&1;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&2;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&3;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&4;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo n °&5;](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxstatusbar.h  
  
##  <a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout  

  
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
  
##  <a name="commandtoindex"></a>CMFCStatusBar::CommandToIndex  

  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIDFind`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="create"></a>CMFCStatusBar::Create  

  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParentWnd`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="createex"></a>CMFCStatusBar::CreateEx  

  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParentWnd`  
 [in] `dwCtrlStyle`  
 [in] `dwStyle`  
 [in] `nID`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick  
 Active ou désactive la gestion de la souris double-clique sur la barre d’état.  
  
```  
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 Si `TRUE`, activer, double-cliquez sur le traitement de la souris. Sinon, désactivez le traitement de la double-clic de souris.  
  
### <a name="remarks"></a>Remarques  
 Si la barre d’état est activée pour traiter les double-clics, Windows envoie le `WM_COMMAND` notification avec un ID de ressource pour le propriétaire de l’état de la barre chaque fois que l’utilisateur double-clique sur le volet de barre d’état.  
  
##  <a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar  
 Afficher une barre de progression dans le volet spécifié.  
  
```  
void EnablePaneProgressBar(
    int nIndex,  
    long nTotal=100,  
    BOOL bDisplayText=FALSE,  
    COLORREF clrBar=-1,  
    COLORREF clrBarDest=-1,  
    COLORREF clrProgressText=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet dont barre de progression pour l’activer.  
  
 [in] `nTotal`  
 Spécifie la valeur maximale de la barre de progression.  
  
 [in] `bDisplayText`  
 Spécifie si la barre de progression doit afficher la valeur de progression actuelle.  
  
 [in] `clrBar`  
 Spécifie la couleur d’arrière-plan de la barre de progression.  
  
 [in] `clrBarDest`  
 Spécifie la couleur secondaire de l’arrière-plan de barre de progression. Utilisez une valeur autre que `clrBar` à remplir par une couleur de fond dans un dégradé.  
  
 [in] `clrProgressText`  
 Spécifie la couleur du texte de la barre de progression.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez désactiver l’appel de barre de progression `EnablePaneProgressBar` avec `nTotal` la valeur -1. Par défaut `nTotal` est défini à 100. Par conséquent, il est inutile des calculs supplémentaires pour afficher la progression en pourcentage.  
  
 Vous devez passer des valeurs différentes `clrBar` et `clrBarDest` afin que la couleur d’arrière-plan de la barre de progression affiche un fusionnée dans un dégradé de couleur. .  
  
 Pour définir l’état d’avancement, appelez le [CMFCStatusBar::SetPaneProgress](#setpaneprogress) (méthode).  
  
##  <a name="getcount"></a>CMFCStatusBar::GetCount  
 Récupère le nombre de volets dans la barre d’état.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de volets dans la barre d’état.  
  
##  <a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea  

  
```  
BOOL GetDrawExtendedArea() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea  

  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rect`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getitemid"></a>CMFCStatusBar::GetItemID  

  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getitemrect"></a>CMFCStatusBar::GetItemRect  

  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo  

  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress  

  
```  
long GetPaneProgress(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle  

  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpanetext"></a>CMFCStatusBar::GetPaneText  

  
```  
void GetPaneText(
    int nIndex,  
    CString& s) const;  
  
CString GetPaneText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `s`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth  
 Récupère la largeur du volet de barre d’état.  
  
```  
int GetPaneWidth(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet de barre d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur du volet de barre d’état qui `nIndex` spécifie ; sinon, zéro si un volet de barre d’état n’existe pas.  
  
##  <a name="gettiptext"></a>CMFCStatusBar::GetTipText  
 Récupérer le texte info-bulle du volet d’une barre état.  
  
```  
CString GetTipText(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet pour lequel récupérer le texte info-bulle.  
  
### <a name="return-value"></a>Valeur de retour  
 Le texte d’info-bulle du volet de barre d’état qui `nIndex` spécifie. Sinon, la chaîne vide si un volet de barre d’état n’existe pas pour l’objet `nIndex` ou si son texte d’info-bulle est vide.  
  
##  <a name="invalidatepanecontent"></a>CMFCStatusBar::InvalidatePaneContent  
 Invalider le volet de barre d’état et renouveler son contenu.  
  
```  
void InvalidatePaneContent(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet dont le contenu doit être invalidés et redessinés.  
  
### <a name="remarks"></a>Remarques  
 Lorsque la barre d’état est invalidée, il est marqué pour être redessiné. Windows redessine lorsque la `UpdateWindow` méthode envoie un `WM_PAINT` de message pour le `OnPaint` (méthode).  
  
##  <a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane  
 Redessiner le volet de la barre d’état.  
  
```  
virtual void OnDrawPane(
    CDC* pDC,  
    CMFCStatusBarPaneInfo* pPane);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique pour le dessin.  
  
 [in] `pPane`  
 Un pointeur vers un `CMFCStatusBarPaneInfo` structure qui contient des informations sur le volet à être redessiné.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, `OnDrawPane` redessine le volet à l’aide du contexte de périphérique `pDC` en fonction de style et le contenu de celui-ci.  
  
 Substituez cette méthode dans un `CMFCStatusBar`-dérivée de la classe pour personnaliser l’apparence d’un volet.  
  
##  <a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow  

  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `cs`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea  

  
```  
void SetDrawExtendedArea(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setindicators"></a>CMFCStatusBar::SetIndicators  

  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpIDArray`  
 [in] `nIDCount`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation  
 Assigne une animation dans le volet spécifié.  
  
```  
void SetPaneAnimation(
    int nIndex,  
    HIMAGELIST hImageList,  
    UINT nFrameRate=500,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet auquel vous souhaitez lui attribuer une animation.  
  
 [in] `hImageList`  
 Spécifie un handle de la liste d’images contenant les images d’animation.  
  
 [in] `nFrameRate`  
 Spécifie la fréquence d’images, en millisecondes, pour l’animation.  
  
 [in] `bUpdate`  
 Si `TRUE`, mettre à jour le volet de contenu immédiatement. Dans le cas contraire, le volet de contenu est mis à jour lorsqu’elle est invalidée.  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez désactiver l’animation en cours, appelez `SetPaneAnimation` avec `hImageList` la valeur `NULL`.  
  
##  <a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor  
 Définit la couleur d’arrière-plan du volet de barre d’état.  
  
```  
void SetPaneBackgroundColor(
    int nIndex,  
    COLORREF clrBackground=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet pour lequel définir une couleur d’arrière-plan.  
  
 [in] `clrBackground`  
 Spécifie la couleur d’arrière-plan.  
  
 [in] `bUpdate`  
 Si `TRUE`, mettre à jour le volet de contenu immédiatement. Dans le cas contraire, ne pas à jour le volet de contenu jusqu'à ce que le volet est invalidé par une autre méthode.  
  
##  <a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon  
 Définir l’icône du volet de barre d’état.  
  
```  
void SetPaneIcon(
    int nIndex,  
    HICON hIcon,  
    BOOL bUpdate=TRUE);

 
void SetPaneIcon(
    int nIndex,  
    HBITMAP hBmp,  
    COLORREF clrTransparent=RGB(255, 0, 255),  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet pour lequel définir l’image.  
  
 [in] `hIcon`  
 Spécifie un handle de l’icône à définir comme l’image du volet.  
  
 [in] `bUpdate`  
 Spécifie s’il faut mettre immédiatement à jour le volet de contenu.  
  
 [in] `hBmp`  
 Spécifie un handle de bitmap par l’image du volet.  
  
 [in] `clrTransparent`  
 Spécifie la couleur transparente de l’image bitmap qui le `hBmp` indique.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez passer soit `HICON` ou `HBITMAP` avec la couleur transparente pour définir image du volet. Si vous ne souhaitez pas afficher l’image de plus, passez la `NULL` valeur en tant que handle de l’image.  
  
 S’il existe une animation en cours d’exécution qui [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) a la valeur, l’animation sera arrêtée.  
  
##  <a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo  

  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `nID`  
 [in] `nStyle`  
 [in] `cxWidth`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress  
 Définir l’indicateur de progression de la barre de progression du volet spécifié.  
  
```  
void SetPaneProgress(
    int nIndex,  
    long nCurr,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet pour laquelle mettre à jour l’indicateur de progression.  
  
 [in] `nCurr`  
 Spécifie la valeur actuelle de l’indicateur de progression.  
  
 [in] `bUpdate`  
 Spécifie si le volet doit être mis à jour immédiatement.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode lorsque vous souhaitez mettre à jour l’indicateur de progression de la barre de progression dans le volet spécifié.  
  
 Pour utiliser cette fonction pour le volet donné, vous devez appeler [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) premier.  
  
##  <a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle  

  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `nStyle`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setpanetext"></a>CMFCStatusBar::SetPaneText  

  
```  
virtual BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 [in] `lpszNewText`  
 [in] `bUpdate`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor  
 Définit la couleur du texte du volet spécifié.  
  
```  
void SetPaneTextColor(
    int nIndex,  
    COLORREF clrText=(COLORREF)-1,  
    BOOL bUpdate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index du volet auquel vous souhaitez affecter une nouvelle couleur de texte.  
  
 [in] `clrText`  
 Spécifie la couleur du texte.  
  
 [in] `bUpdate`  
 Si `TRUE`, mettre à jour le volet de contenu immédiatement. Dans le cas contraire, ne pas à jour le volet de contenu jusqu'à ce que le volet est invalidé par une autre méthode.  
  
##  <a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth  
 Définissez la largeur du volet de barre d’état.  
  
```  
void SetPaneWidth(
    int nIndex,  
    int cx);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Index du volet de barre d’état pour lequel définir une nouvelle largeur.  
  
 [in] `cx`  
 La nouvelle largeur du volet de barre de l’état, en pixels.  
  
##  <a name="settiptext"></a>CMFCStatusBar::SetTipText  
 Définir le texte d’info-bulle d’un volet de barre d’état.  
  
```  
void SetTipText(
    int nIndex,  
    LPCTSTR pszTipText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 L’index du volet auquel vous souhaitez affecter le texte d’info-bulle.  
  
 [in] `pszTipText`  
 Le nouveau texte d’info-bulle.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPane (classe)](../../mfc/reference/cpane-class.md)   
 [CStatusBar (classe)](../../mfc/reference/cstatusbar-class.md)

