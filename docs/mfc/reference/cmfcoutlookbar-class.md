---
title: Classe de CMFCOutlookBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar class
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
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
ms.openlocfilehash: ff58cf786e4979d64aa2b5d7ad4d1a32b96bec3d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar, Classe
Volet à onglets avec l'apparence visuelle du **Volet de navigation** dans Microsoft Outlook 2000 et Outlook 2003. Le `CMFCOutlookBar` objet contient un [CMFCOutlookBarTabCtrl classe](../../mfc/reference/cmfcoutlookbartabctrl-class.md) objet et une série d’onglets. Les onglets peuvent être des [CMFCOutlookBarPane classe](../../mfc/reference/cmfcoutlookbarpane-class.md) objets ou `CWnd`-objets dérivés. Pour l'utilisateur, la barre Outlook apparaît comme un ensemble de boutons et une zone d'affichage. Lorsque l'utilisateur clique sur un bouton, le volet de contrôle ou de bouton correspondant s'affiche.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Constructeur par défaut.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Spécifie si un volet à onglets vide peut être détruit. (Substitue [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Détermine si un autre volet peut être ancré dans le volet de barre Outlook. (Remplace CDockablePane::CanAcceptPane).|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Détermine si la légende pour le volet à onglets affiche le même texte que l’onglet actif. (Substitue [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Crée le contrôle de barre Outlook.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Crée un onglet de barre Outlook personnalisé.|  
|`CMFCOutlookBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Détermine si un utilisateur peut s’ancrer une barre de contrôle sur le bord extérieur de la barre Outlook.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Fait flotter un volet, mais seulement si le volet réside actuellement dans un onglet détachable. (Substitue [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Retourne la police du texte sur les boutons de la barre Outlook.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Retourne la taille et la position des zones d’onglet dans la barre Outlook. (Substitue [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Détermine si le comportement de la barre Outlook reproduit celle de Microsoft Office Outlook 2003 (voir Remarques).|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) une fois que l’onglet actif a été défini à l’aide de l’animation.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) avant d’un onglet de page est définie sous l’onglet actif à l’aide de l’animation.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Appelé par le framework si la barre Outlook fait défiler vers le haut ou vers le bas.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Supprime un onglet de barre Outlook personnalisé.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Définit la police du texte sur les boutons de la barre Outlook.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Spécifie si le comportement de la barre Outlook imite celui d’Outlook 2003 (voir Remarques).|  
  
## <a name="remarks"></a>Remarques  
 Pour obtenir un exemple d’une barre Outlook, consultez le [exemple OutlookDemo : Application de OutlookDemo MFC](../../visual-cpp-samples.md).  
  
## <a name="implementing-the-outlook-bar"></a>L’implémentation de la barre Outlook  
 Pour utiliser le contrôle `CMFCOutlookBar` dans votre application, procédez comme suit :  
  
1.  Incorporez un objet `CMFCOutlookBar` dans la classe de fenêtre frame principale.  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  Lors du traitement de la `WM_CREATE` message dans le frame principal, l’appel de la [CMFCOutlookBar::Create](#create) pour créer le contrôle d’onglet de la barre Outlook.  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  Obtenir un pointeur vers l’objet sous-jacent `CMFCOutlookBarTabCtrl` à l’aide de [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  Créer un [CMFCOutlookBarPane classe](../../mfc/reference/cmfcoutlookbarpane-class.md) objet pour chaque onglet qui contient les boutons.  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  Appelez [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) pour ajouter chaque nouvel onglet. Définir le `bDetachable` paramètre `FALSE` pour créer une page non amovibles. Ou bien, utilisez [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) pour ajouter des pages détachables.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Pour ajouter un `CWnd`-contrôle dérivé (par exemple, [CMFCShellTreeCtrl classe](../../mfc/reference/cmfcshelltreectrl-class.md)) dans un onglet, créez le contrôle et l’appel [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) pour l’ajouter à la barre Outlook.  
  
> [!NOTE]
>  Vous devez utiliser des ID de contrôle unique pour chaque [CMFCOutlookBarPane classe](../../mfc/reference/cmfcoutlookbarpane-class.md) objet et pour chaque `CWnd`-objet dérivé.  
  
 Pour dynamiquement, ajouter ou supprimer des pages lors de l’exécution, utilisez [CMFCOutlookBar::CreateCustomPage](#createcustompage) et [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Mode d’Outlook 2003  
 En mode Outlook 2003, les boutons de l’onglet sont positionnées en bas du volet de barre Outlook. Lorsqu’il n’est pas suffisamment de place pour afficher les boutons, ils sont affichés sous forme d’icônes dans une zone de barre d’outils de type dans la partie inférieure du volet.  
  
 Utilisez [CMFCOutlookBar::SetMode2003](#setmode2003) pour activer le mode d’Outlook 2003. Utilisez [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) pour définir l’image bitmap qui contient les icônes qui sont affichées en bas de la barre Outlook. Les icônes dans le fichier bitmap doivent être triés par l’index de tabulation.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Spécifie si un volet à onglets vide peut être détruit.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un volet à onglets vide peut être détruit ; dans le cas contraire, `FALSE`. Retourne l’implémentation par défaut toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Si un volet à onglets vide ne peut pas être détruit, le framework le masque à la place.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 Détermine si un autre volet peut être ancré dans le volet de barre Outlook.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Pointeur vers un autre volet qui est en cours ancré dans ce volet.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un autre volet peut être ancré dans le volet de barre Outlook ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Si la barre Outlook est en mode de Outlook 2003, ancrage n'est pas pris en charge, la valeur de retour est `FALSE`.  
  
 Si le `pBar` paramètre est `NULL`, cette méthode retourne `FALSE`.  
  
 Sinon, cette méthode se comporte comme la méthode de base [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), sauf que même si la station d’accueil n’est pas activée, une barre Outlook permet toujours une autre barre Outlook être ancré sur celui-ci.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 Détermine si la légende pour le volet à onglets affiche le même texte que l’onglet actif.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la légende de la fenêtre de la barre Outlook est automatiquement définie sur le texte de l’onglet actif ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) pour activer ou désactiver cette fonctionnalité.  
  
 En mode Outlook 2003, ce paramètre est toujours activé.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Crée le contrôle de barre Outlook.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszCaption`  
 Spécifie la légende de fenêtre.  
  
 [in] `pParentWnd`  
 Spécifie un pointeur vers une fenêtre parente. Il ne doit pas être NULL.  
  
 [in] `rect`  
 Spécifie la taille et la position en pixels de la barre outlook.  
  
 [in] `nID`  
 Spécifie l’ID de contrôle. Doivent être distingués des autres identificateurs utilisés dans l’application de contrôle.  
  
 [in] `dwStyle`  
 Spécifie le style de barre de contrôle souhaité. Pour les valeurs possibles, consultez la page [Styles de fenêtre](../../mfc/reference/window-styles.md).  
  
 [in] `dwControlBarStyle`  
 Spécifie les styles spéciaux définis par la bibliothèque.  
  
 [in] `pContext`  
 Créer le contexte.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous construisez un `CMFCOutlookBar` objet en deux étapes. Tout d’abord appeler le constructeur, puis appelez `Create`, ce qui crée le contrôle de barre outlook et l’attache à le `CMFCOutlookBar` objet.  
  
 Consultez la page [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) pour obtenir la liste des styles disponibles bibliothèque définie par `dwControlBarStyle`.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `Create` procédé de la `CMFCOutlookBar` classe. Cet extrait de code fait partie de la [Outlook plusieurs vues, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews n °&1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews n °&2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
 Crée un onglet de barre Outlook personnalisé.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszPageName`  
 L’étiquette de la page.  
  
 [in] `bActivatePage`  
 Si `TRUE`, la page devient active lors de la création.  
  
 [in] `dwEnabledDocking`  
 Une combinaison d’indicateurs CBRS_ALIGN_ qui spécifie les côtés d’ancrage activées lorsque la page est détachée.  
  
 [in] `bEnableTextLabels`  
 Si `TRUE`, les étiquettes de texte sont activés pour les boutons qui se trouvent sur la page.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la page qui vient d’être créée, ou `NULL` si la création a échoué.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour permettre aux utilisateurs de créer des pages personnalisées de barre Outlook. Vous pouvez créer jusqu'à 100 pages par application. Le contrôle de page ID démarrent à partir de 0xF000. La création échoue si le nombre total de pages de la barre Outlook personnalisées est supérieure à 100.  
  
 Utilisez [CMFCOutlookBar::RemoveCustomPage](#removecustompage) pour supprimer des pages personnalisées.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 Spécifie si un utilisateur pouvez ancrer un volet sur le bord extérieur de la barre Outlook.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L'implémentation par défaut retourne la valeur `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle la `DoesAllowDynInsertBefore` méthode lorsqu’il recherche un emplacement ancrer un volet dynamique. Si la fonction retourne `FALSE`, le framework n’autorise pas l’ancrage de n’importe quel volet dynamique aux bords externes du volet.  
  
 En règle générale, vous créez une barre Outlook comme un contrôle statique non flottant. Vous pouvez remplacer cette fonction dans une classe dérivée et retour `TRUE` pour modifier ce comportement.  
  
> [!NOTE]
>  Étant donné que les volets dynamiques vérifier l’état ancré volets statique lors de l’ancrage, vous devez volets d’ancrage dynamiques après les volets statiques chaque fois que possible.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 Flotte d’un volet.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pBar`  
 Pointeur vers le volet à virgule flottante.  
  
 [in] `nTabID`  
 Index de base zéro de l’onglet à virgule flottante.  
  
 [in] `dockMethod`  
 Spécifie la méthode à utiliser pour détacher le volet.  Pour plus d’informations, consultez [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in] `bHide`  
 `TRUE`Pour masquer le volet avant flottante. dans le cas contraire, `FALSE`. Contrairement à la version de la classe de base de cette méthode, ce paramètre n’a pas de valeur par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet flotte ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est similaire à [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) , sauf qu’elle ne permet pas le dernier onglet restant sur un contrôle de barre Outlook pour float.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Retourne la police du texte sur la page d’onglets du bouton de la barre Outlook.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’objet de police qui est utilisé pour afficher du texte dans Outlook barre des onglets de la page.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour extraire la police utilisée pour afficher le texte sur les onglets bouton Outlook. Vous pouvez définir la police en appelant sur [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Détermine la taille et la position des zones d’onglet dans la barre Outlook.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rectTabAreaTop`  
 Contient la taille et position (dans les coordonnées clientes) de la zone d’onglet supérieur au retour de fonction.  
  
 [out] `rectTabAreaBottom`  
 Lorsque la fonction retourne, contient la taille et position (dans les coordonnées clientes) de la zone de l’onglet en bas.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle cette méthode pour déterminer le type d’ancrage dans le volet cible. Lorsque le framework détermine que l’utilisateur fait glisser le volet pour être ancré sur la zone de l’onglet du volet cible, il tente d’ajouter le premier volet sous un nouvel onglet du volet cible. Dans le cas contraire, il essaie d’ancrage du premier volet côté approprié du volet cible. L’infrastructure crée un conteneur avec un curseur pour accueillir le volet ancré supplémentaire.  
  
 L’implémentation par défaut de `GetTabArea` retourne toute la zone cliente de la barre Outlook si la barre Outlook est statique ; c'est-à-dire, si la barre Outlook ne peut pas faire flotter. Sinon, elle retourne la zone de boutons de page prennent en haut et bas du contrôle de barre Outlook.  
  
 Substituez cette méthode dans une classe dérivée de `CMFCOutlookBar` pour modifier ce comportement.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Spécifie si le comportement de la barre Outlook reproduit celle de Microsoft Office Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la barre Outlook s’exécute en mode de Microsoft Office 2003 ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez activer ce mode en utilisant [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) une fois que l’onglet actif a été défini à l’aide de l’animation.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nPage`  
 Index de base zéro de la page d’onglets qui est devenue active.  
  
### <a name="remarks"></a>Remarques  
 L’effet visuel de la configuration de l’onglet actif dépend de si vous avez activé l’animation. Pour plus d’informations, consultez [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) avant d’un onglet de page est définie sous l’onglet actif à l’aide de l’animation.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nPage`  
 Index de base zéro de la page d’onglets qui doit être défini actif.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si l’animation doit être utilisée lors de la définition du nouvel onglet actif, ou `FALSE` si l’animation doit être désactivée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Appelé par le framework si la barre Outlook fait défiler vers le haut ou vers le bas.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDown`  
 `TRUE`Si la barre Outlook fait défiler vers le bas, ou `FALSE` si elle est défilement vers le haut.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 Supprime une page d’onglet de barre Outlook personnalisée.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiPage`  
 Index de base zéro de la page dans la fenêtre Outlook parente.  
  
 [in] `pTargetWnd`  
 Pointerto la fenêtre Outlook parente.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la page personnalisée a été supprimée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour supprimer des pages personnalisées. Lorsque la page est supprimée, son ID de contrôle est retournée au pool d’ID disponibles.  
  
 Vous devez fournir un pointeur vers [CMFCOutlookBarTabCtrl classe](../../mfc/reference/cmfcoutlookbartabctrl-class.md) de l’objet dans lequel réside la page doit être supprimé actuellement. Notez qu’un utilisateur peut déplacer des pages détachables entre différentes barres Outlook, mais les informations sur une page personnalisée se trouvent dans l’objet de barre Outlook pour laquelle vous avez appelé [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Utilisez [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) pour obtenir un pointeur vers la fenêtre Outlook.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Définit la police du texte sur les boutons de la barre Outlook.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFont`  
 Spécifie la nouvelle police.  
  
 [in] `bRedraw`  
 Si `TRUE`, la barre Outlook est redessinée.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour définir une police pour le texte affiché sur les boutons de page d’onglet outlook.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Spécifie si le comportement de la barre Outlook imite celui d’Outlook 2003.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bMode2003`  
 Si la valeur est TRUE, le mode d’Office 2003 est activé.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet d’activer ou désactiver le mode d’Office 2003. Dans ce mode, la barre Outlook possède une barre d’outils supplémentaire avec un bouton de personnalisation. Le comportement de la barre Outlook est conforme au comportement de la barre Outlook dans Microsoft Office 2003.  
  
 Par défaut, ce mode est désactivé.  
  
> [!NOTE]
>  Cette fonction doit être appelée avant [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane (classe)](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl (classe)](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane (classe)](../../mfc/reference/cmfcoutlookbarpane-class.md)

