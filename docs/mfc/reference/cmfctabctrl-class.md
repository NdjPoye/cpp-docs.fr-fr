---
title: Classe de CMFCTabCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabCtrl::SwapTabs method
- CMFCTabCtrl constructor
- CMFCTabCtrl::MoveTab method
- CMFCTabCtrl::GetTabFromPoint method
- CMFCTabCtrl::PreTranslateMessage method
- CMFCTabCtrl::RecalcLayout method
- CMFCTabCtrl class
- CMFCTabCtrl::IsPtInTabArea method
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
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
ms.openlocfilehash: 595ff7fbcd55f3b756ce650e02b6247b898d7629
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
La `CMFCTabCtrl` classe fournit les fonctionnalités d’un contrôle onglet. Le contrôle onglet affiche une fenêtre ancrable avec des onglets plats ou tridimensionnels en haut ou en bas. Les onglets peuvent afficher un texte et une image et peuvent changer de couleur en cas d'activation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Constructeur par défaut.|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|Affiche l’onglet spécifié du contrôle d’onglet actuelle et définit le focus sur cet onglet.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Spécifie si l’infrastructure consiste à redimensionner la zone cliente de toutes les fenêtres de contrôle onglet lorsqu’un élément d’interface utilisateur de la modification du contrôle onglet.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Réduit la forme la taille de la zone de l’onglet spécifié. (Substitue `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Crée le contrôle onglet et l’attache à le `CMFCTabCtrl` objet.|  
|`CMFCTabCtrl::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Affiche ou masque le bouton Fermer ( **X**) sur l’onglet actif.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Active ou désactive les étiquettes de l’onglet modifiable. (Substitue [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Remplace les deux boutons, faites défiler les onglets de la fenêtre avec un bouton qui ouvre un menu de fenêtres à onglets.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Garantit qu’un onglet est visible.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Récupère le symbole qui est associé à un onglet dans un menu contextuel des fenêtres à onglets.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Récupère l’index du premier onglet est visible dans le contrôle onglet en cours.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Récupère une valeur qui spécifie comment le contrôle onglet en cours peut être redimensionné.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Récupère un pointeur vers l’objet de barre de défilement qui est associé au contrôle onglet.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Récupère le rectangle englobant de la zone d’étiquette onglet en haut ou en bas du contrôle d’onglet. (Substitue [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Récupère l’onglet qui contient un point spécifié. (Substitue [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Récupère la largeur maximale d’un onglet.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Récupère la hauteur de la zone des onglets du contrôle onglet actuel.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Récupère un rectangle qui délimite la zone des onglets du contrôle onglet actuel. (Substitue [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Récupère les limites de la zone cliente du contrôle d’onglet actuel.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Masque la barre de défilement horizontale éventuel de la fenêtre active.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Spécifie si l’infrastructure est d’afficher des fenêtres de contrôle onglet inactif.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Active ou désactive la zone de l’onglet de dessin si aucun onglet visible.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Active ou désactive le dessin d’un onglet lorsqu’il existe une seule fenêtre à onglets. (Substitue [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Indique si l’onglet actif d’un contrôle onglet est l’onglet actif dans un groupe d’onglets interface plusieurs documents.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Indique si le texte de l’onglet actif est affiché à l’aide d’une police en gras.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Indique si le bouton Fermer ( **X**) s’affiche sur l’onglet actif ou le coin supérieur droit de la zone de l’onglet.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Indique si la fenêtre à onglets Dessine un rectangle de cadre autour des volets incorporés.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Indique si le frame autour de la zone de l’onglet 2D ou 3D.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Indique si l’apparence des onglets dans le contrôle onglet en cours est plat ou non.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Indique si l’apparence de la gauche et droite d’un onglet dans le contrôle onglet en cours est arrondie.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Indique si le contrôle onglet en cours est contenu dans la zone cliente d’une fenêtre d’interface multidocument.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Indique si le contrôle onglet en cours est affiché dans le style de Microsoft OneNote.|  
|`CMFCTabCtrl::IsPtInTabArea`|Détermine si un point est à l’intérieur de la zone de l’onglet. (Substitue [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Indique si le contrôle onglet actuel possède une barre de défilement qui peut faire défiler ses onglets en tant que groupe.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Indique si le contrôle onglet affiche les boutons de défilement ou un bouton qui affiche un menu de fenêtres à onglets.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Indique si les onglets s’affichent dans le style de Visual Studio .NET 2005.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Spécifie l’apparence des onglets dans le contrôle onglet en cours.|  
|`CMFCTabCtrl::MoveTab`|Déplace un onglet vers un autre onglet. (Substitue [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|Appelé par l’infrastructure lorsque le curseur est déplacé tout d’abord dans la fenêtre de contrôle onglet.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Appelé par l’infrastructure pendant une opération glisser lorsque la souris est placée sur la fenêtre cible de déplacement. (Substitue [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Affiche un menu contextuel des fenêtres à onglets, attend que l’utilisateur sélectionne un onglet et rend l’onglet sélectionné l’onglet actif.|  
|`CMFCTabCtrl::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Recalcule la disposition du contrôle d’onglet interne. (Substitue [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Définit l’onglet actif d’un contrôle onglet en tant que l’onglet actif dans un groupe d’onglets interface plusieurs documents.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Active un onglet. (Substitue [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Active ou désactive l’utilisation d’une police en gras dans les onglets.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Active ou désactive le rectangle de trame drawinga autour d’une barre incorporée.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Spécifie s’il faut dessiner plat ou une image 3D autour de la zone de l’onglet.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Spécifie une liste d’images. (Substitue [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Spécifie comment le contrôle onglet en cours peut être redimensionné et réaffiche ensuite le contrôle.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|Spécifie la largeur de l’onglet maximale dans une fenêtre à onglets.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Met fin à l’opération en cours de redimensionnement du contrôle onglet.|  
|`CMFCTabCtrl::SwapTabs`|Permute les deux onglets. (Substitue [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Dessine une barre de défilement horizontal d’un contrôle onglet qui affiche les onglets plats.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Empêche la vue active de perdre le focus lorsqu’un nouvel onglet est inséré et activé.|  
  
## <a name="remarks"></a>Remarques  
 La `CMFCTabCtrl` classe prend en charge :  
  
-   Onglet styles de contrôle incluent 3D, plat et plat avec une barre de défilement horizontale partagé.  
  
-   Onglets situés en haut ou en bas de la fenêtre.  
  
-   Onglets qui affichent du texte, images, ou du texte et images.  
  
-   Onglets qui changent de couleur lorsque l’onglet est actif.  
  
-   Modifications de taille de bordure pour les onglets réglables.  
  
-   Fenêtres à onglets détachables.  
  
 Le `CMFCTabCtrl` classe peut être utilisée avec une boîte de dialogue, mais est conçu pour le contrôle des applications qui utilisent l’ancrage barres comme [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] et [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Pour plus d’informations, consultez [CDockablePane Class](../../mfc/reference/cdockablepane-class.md).  
  
 Suivez ces étapes pour ajouter un redimensionnables, ancrage du contrôle d’onglet dans votre application :  
  
1.  Créez une instance de [CTabbedPane classe](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Appelez [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Utilisez [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) ou [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) pour ajouter de nouveaux onglets.  
  
4.  Appelez [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) afin que le contrôle onglet d’accueil actuel ancrer à la fenêtre frame principale.  
  
5.  Appelez [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) pour ancrer la fenêtre à onglets dans le frame principal.  
  
 Pour obtenir un exemple montrant comment créer une fenêtre avec onglets, comme une barre d’ancrage de contrôles, consultez [CTabbedPane classe](../../mfc/reference/ctabbedpane-class.md). Pour utiliser `CMFCTabCtrl` comme un contrôle non ancrage, créer un `CMFCTabCtrl` de l’objet, puis appelez [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans le `CMFCTabCtrl` classe pour configurer un `CMFCTabCtrl` objet. L’exemple explique comment ajouter un onglet, afficher le bouton Fermer dans l’onglet actif, activer les étiquettes de l’onglet modifiable et afficher un menu contextuel des étiquettes de fenêtre à onglets. Cet exemple fait partie de la [échantillon de collecte de l’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection n °&1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection n °&3;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 Affiche l’onglet spécifié du contrôle d’onglet actuelle et définit le focus sur cet onglet.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTab`  
 Index de base zéro d’un onglet à afficher, ou -1 pour indiquer l’onglet actif.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 Spécifie si l’infrastructure consiste à redimensionner la zone cliente de toutes les fenêtres de contrôle onglet lorsqu’un élément d’interface utilisateur de la modification du contrôle onglet.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bAutoSize`  
 `TRUE`redimensionner automatiquement les fenêtres de contrôle onglet. dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
 Crée le contrôle onglet et l’attache à le `CMFCTabCtrl` objet.  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `style`  
 Le style du contrôle onglet. Pour plus d'informations, consultez la section Notes.  
  
 [in] `rect`  
 Un rectangle qui délimite le contrôle onglet.  
  
 [in] `pParentWnd`  
 Pointeur vers une fenêtre parente. Ne doit pas être `NULL`.  
  
 [in] `nID`  
 L’ID du contrôle d’onglet.  
  
 [in] `location`  
 L’emplacement des onglets. La valeur par défaut est `LOCATION_BOTTOM`. Pour plus d'informations, consultez la section Notes.  
  
 [in] `bCloseBtn`  
 `TRUE`Pour afficher un bouton de fermeture dans l’onglet ; dans le cas contraire, `FALSE`. La valeur par défaut est `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Le tableau suivant décrit les valeurs que vous pouvez spécifier pour le `style` paramètre.  
  
|Style|Description|  
|-----------|-----------------|  
|STYLE_3D|Crée un contrôle onglet avec une apparence en trois dimensions.|  
|STYLE_FLAT|Crée un contrôle onglet avec onglets plats.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Crée un contrôle onglet avec onglets plats et une barre de défilement qui peut faire défiler les onglets s’ils sont réduits par une fenêtre parente.|  
|STYLE_3D_ONENOTE|Crée un contrôle onglet dans le style de Microsoft OneNote.|  
|STYLE_3D_VS2005|Crée un contrôle onglet dans le style de Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED|Crée un contrôle onglet avec onglets arrondis dans le style de Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED_SCROLL|Crée un contrôle onglet avec onglets arrondis et des boutons de défilement dans le style de Microsoft Visual Studio 2005.|  
  
 Le tableau suivant répertorie les valeurs que vous pouvez spécifier pour le `location` paramètre.  
  
|Emplacement|Description|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Onglets sont situés en bas du contrôle d’onglet.|  
|LOCATION_TOP|Onglets sont situés en haut du contrôle onglet.|  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `Create` méthode dans la `CMFCTabCtrl` classe. Cet exemple fait partie de la [échantillon de collecte de l’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection n °&1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection n °&2;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 Réduit la forme la taille de la zone de l’onglet spécifié.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rectEdit`  
 Rectangle qui spécifie la zone d’un onglet.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée lorsque vous modifiez l’étiquette d’un onglet. Cette méthode réduit la forme les côtés gauche et droit du rectangle spécifié par la moitié de la hauteur onglet actuel et réduit la forme du haut et bas d’une unité.  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 Affiche ou masque le bouton Fermer ( **X**) sur l’onglet actif.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour afficher le bouton Fermer sous l’onglet actif ; `FALSE` pour afficher le bouton Fermer dans le coin supérieur droit de la zone de l’onglet. La valeur par défaut est `TRUE`.  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 Active ou désactive les étiquettes de l’onglet modifiable.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour activer les étiquettes de l’onglet modifiable ; `FALSE` pour désactiver les étiquettes de l’onglet modifiable.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 Bascule entre une interface utilisateur qui utilise les deux boutons pour faire défiler les onglets de la fenêtre et une interface qui affiche un menu contextuel des fenêtres à onglets.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour afficher un menu contextuel des étiquettes de la fenêtre à onglets ; `FALSE` pour afficher les boutons de défilement vers l’avant et vers l’arrière. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur clique sur une étiquette de l’onglet, le framework affiche la fenêtre à onglets correspondante. Si l’étiquette de l’onglet est visible, la fenêtre à onglets s’ouvre sans modifier sa position. Si l’utilisateur sélectionne un document dans le menu contextuel et la fenêtre à onglets correspondante est hors écran, la fenêtre à onglets devient le premier onglet.  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 Garantit qu’un onglet est visible.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iTab`  
 Index de base zéro d’un onglet.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’opération a réussi ; `FALSE` si le `iTab` index de paramètre n’est pas valide.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour garantir que l’onglet spécifié est visible. Le contrôle onglet défilera si nécessaire.  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 Extrait l’image qui est associé à un onglet dans un menu contextuel des fenêtres à onglets.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nCmdID`  
 L’ID de commande d’un onglet dans un menu contextuel des fenêtres à onglets.  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle d’une image bitmap.  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 Récupère l’index du premier onglet est visible dans le contrôle onglet en cours.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro d’un onglet dans le contrôle onglet.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode uniquement lorsque le contrôle d’onglet est affiché dans le style de Microsoft OneNote. Utilisez le [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) méthode pour déterminer le style.  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 Récupère une valeur qui spécifie comment le contrôle onglet en cours peut être redimensionné.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Parmi les `CMFCTabCtrl::ResizeMode` des valeurs d’énumération qui spécifie comment le contrôle onglet peut être redimensionné. Pour obtenir la liste des valeurs possibles, consultez la section Notes de la [CMFCTabCtrl::SetResizeMode](#setresizemode) (méthode).  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 Récupère un pointeur vers l’objet de barre de défilement qui est associé au contrôle onglet.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un ou un pointeur vers un objet de barre de défilement `NULL` si le contrôle onglet n’a pas été créé à l’aide de la `STYLE_FLAT_SHARED_HORZ_SCROLL` style.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour accéder à la barre de défilement incorporé du contrôle onglet. Un objet de barre de défilement est créé uniquement lorsque le contrôle onglet possède le `STYLE_FLAT_SHARED_HORZ_SCROLL` style.  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 Récupère le rectangle englobant de la zone d’étiquette onglet en haut ou en bas du contrôle d’onglet.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rectTabAreaTop`  
 Lorsque cette méthode est retournée, cette référence contient un rectangle qui délimite la zone d’étiquette onglet supérieur. Le rectangle est en coordonnées clientes. Cette référence est vide si aucune zone d’étiquette onglet n’existe en haut du contrôle onglet.  
  
 [out] `rectTabAreaBottom`  
 Lorsque cette méthode est retournée, cette référence contient un rectangle qui délimite la zone étiquette de l’onglet en bas. Le rectangle est en coordonnées clientes. Cette référence est vide si aucune zone d’étiquette onglet n’existe en bas du contrôle d’onglet.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour déterminer la taille et la position de la zone d’onglet dans la fenêtre à onglets.  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 Récupère la largeur maximale d’un onglet.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Largeur maximale d’un onglet, en pixels. Si la valeur de retour est 0, la largeur de l’onglet est illimitée.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) pour définir la largeur de l’onglet maximale.  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 Récupère la hauteur de la zone des onglets du contrôle onglet actuel.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur de la zone de l’onglet si aucun onglet n’est visible, ou zéro si aucun onglet n’est visible.  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 Récupère un rectangle qui délimite la zone des onglets du contrôle onglet actuel.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rect`  
 Lorsque cette méthode est retournée, la `rect` paramètre contient un rectangle qui délimite la zone de l’onglet.  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 Récupère les limites de la zone cliente du contrôle d’onglet actuel.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `rect`  
 Lorsque cette méthode est retournée, ce paramètre contient un rectangle qui délimite le contrôle onglet en cours.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Masque la barre de défilement horizontale, éventuellement, dans la fenêtre active.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour empêcher le contrôle onglet clignote lorsque l’utilisateur bascule entre les onglets du contrôle.  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 Spécifie si le framework affiche les fenêtres de contrôle onglet inactif.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bHide`  
 `TRUE`ne pas afficher une fenêtre inactive ; `FALSE` pour afficher une fenêtre inactive. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 Active ou désactive le dessin de la zone de l’onglet si aucun onglet visible.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bHide`  
 `TRUE`Pour activer le dessin de la zone de l’onglet ; `FALSE` pour désactiver le dessin. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 Active ou désactive le dessin de l’onglet s’il existe une seule fenêtre à onglets.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bHide`  
 `TRUE`ne pas dessiner un onglet pour une seule fenêtre à onglets ; `FALSE` pour dessiner un onglet unique. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 Indique si l’onglet actif d’un contrôle onglet est l’onglet actif dans un groupe d’onglets interface plusieurs documents.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’onglet actif d’un contrôle onglet est l’onglet actif dans un groupe d’onglets MDI ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez organiser plusieurs fenêtres de document en deux groupes d’onglets verticaux ou horizontaux et transférer aisément des documents à partir du groupe d’un onglet à l’autre.  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 Indique si le texte de l’onglet actif est affiché à l’aide d’une police en gras.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’onglet actif est affiché à l’aide de la police en gras. dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Utilisez le [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) méthode pour modifier la police de l’onglet actif.  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 Indique si le bouton Fermer ( **X**) s’affiche sur l’onglet actif ou dans le coin supérieur droit de la zone de l’onglet.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le bouton Fermer est affiché sous l’onglet actif ; `FALSE` si le bouton Fermer est affiché dans le coin supérieur droit de la zone de l’onglet.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 Indique si la fenêtre à onglets Dessine un rectangle de cadre autour des volets incorporés.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un rectangle de frame est dessiné ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [CMFCTabCtrl::SetDrawFrame](#setdrawframe) méthode pour activer ou désactiver le dessin d’un rectangle de frame.  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 Indique si le frame autour de la zone de l’onglet 2D ou 3D.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le frame autour de la zone de l’onglet est plat ; `FALSE` si l’image est en trois dimensions.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [CMFCTabCtrl::SetFlatFrame](#setflatframe) méthode pour modifier la façon dont le frame est dessiné.  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 Indique si l’apparence des onglets dans le contrôle onglet en cours est plat ou non.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’apparence des onglets dans le contrôle onglet en cours est plat ; dans le cas contraire, `FALSE`.  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 Indique si l’apparence de la gauche et droite d’un onglet dans le contrôle onglet en cours est arrondie.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les côtés de chaque onglet est arrondie ; dans le cas contraire, `FALSE`.  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 Indique si le contrôle onglet en cours est contenu dans la zone cliente d’une fenêtre d’interface multidocument.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le contrôle onglet en cours se trouve dans une fenêtre de la zone cliente MDI ; dans le cas contraire, `FALSE`.  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Indique si le contrôle onglet en cours est affiché dans le style de Microsoft OneNote.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le contrôle d’onglet est affiché dans le style de Microsoft OneNote ; dans le cas contraire, `FALSE`.  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 Indique si le contrôle onglet actuel possède une barre de défilement qui peut faire défiler ses onglets en tant que groupe.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le contrôle onglet possède une barre de défilement partagé ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne `TRUE` si le `style` paramètre de la [CMFCTabCtrl::Create](#create) STYLE_FLAT_SHARED_HORZ_SCROLL, il suffit.  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 Indique si le contrôle onglet affiche les boutons de défilement ou un bouton qui affiche un menu de fenêtres à onglets.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les fenêtres à onglets défile à l’aide d’un menu contextuel d’étiquette de fenêtre à onglets. `FALSE` si les fenêtres à onglets défile à l’aide des boutons de défilement vers l’avant et vers l’arrière.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) méthode pour spécifier la méthode de défilement des fenêtres avec onglet.  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Indique si les onglets sont dessinés à l’aide du style de Visual Studio 2005.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les onglets sont dessinées à l’aide du style de Visual Studio 2005 ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `style` paramètre de la [CMFCTabCtrl::Create](#create) méthode pour spécifier comment les onglets sont dessinés.  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 Empêche la vue active de perdre le focus lorsqu’un nouvel onglet est inséré et activé.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Notes  
 Le focus est généralement effectuée par une nouvelle fenêtre à onglets lorsque l’onglet est inséré et devient actif. Définir le `CMFCTabCtrl::m_bEnableActivate` variable de membre pour `FALSE` pour conserver le focus d’origine. La valeur par défaut est `TRUE`.  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 Spécifie l’apparence des onglets dans le contrôle onglet en cours.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `style`  
 Une des valeurs d’énumération qui spécifie l’apparence du contrôle d’onglet. Pour plus d’informations, consultez le tableau dans la section Notes.  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 La valeur de la `style` paramètre peut prendre l’une des opérations suivantes `CMFCTabCtrl::Style` énumérations.  
  
|Nom|Description|  
|----------|-----------------|  
|STYLE_3D|Affiche les onglets en trois dimensions, rectangulaires qui ont des angles arrondis.|  
|STYLE_3D_ONENOTE|Affiche les onglets en trois dimensions qui ont un côté vertical et un côté incliné et qui ont des angles arrondis.|  
|STYLE_3D_ROUNDED|Affiche les onglets en trois dimensions incliné côtés et aux angles arrondis.|  
|STYLE_3D_ROUNDED_SCROLL|Affiche les onglets en trois dimensions incliné côtés et aux angles arrondis. S’il y a plus d’onglets peuvent être affichées en même temps, l’infrastructure affiche une liste déroulante et un menu des onglets pour rendre active.|  
|STYLE_3D_SCROLLED|Affiche les onglets en trois dimensions, rectangulaires. S’il y a plus d’onglets peuvent être affichées en même temps, l’infrastructure affiche une liste déroulante et un menu des onglets pour rendre active.|  
|STYLE_3D_VS2005|Affiche en trois dimensions, arrondi à onglets qui ont un côté incliné et un côté vertical.|  
|STYLE_FLAT|Affiche les onglets à deux dimensions qui ont incliné côtés gauche et droit.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Affiche les onglets à deux dimensions. S’il y a plus d’onglets peuvent être affichées en même temps, le framework affiche les flèches de défilement à la fin de la zone de l’onglet.|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 Appelé par l’infrastructure lors d’une opération de glisser-déplacer lorsque le curseur entre d’abord dans la fenêtre du contrôle d’onglet actuel.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDataObject`  
 Pointe vers un objet de données qui contient les données que l’utilisateur fait glisser.  
  
 [in] `dwKeyState`  
 Contient l’état des touches de modification. Ce paramètre est une combinaison d’opérations de bits (OR) des valeurs suivantes : `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, et `MK_RBUTTON`. Pour plus d’informations, consultez la **Message paramètres** section de [sur l’entrée de souris](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Contient l’emplacement actuel du curseur en coordonnées clientes.  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `DROPEFFECT_NONE`, ce qui signifie que la cible de déplacement ne peut pas accepter les données.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour prendre en charge une opération de glisser-déplacer. Substituez cette méthode pour implémenter votre propre comportement personnalisé.  
  
 Par défaut, cette méthode appelle uniquement `CMFCTabCtrl::OnDragOver`, qui retourne toujours `DROPEFFECT_NONE`.  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 Appelé par l’infrastructure pendant une opération glisser lorsque la souris est placée sur la fenêtre cible de déplacement.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDataObject`  
 Pointeur vers un [COleDataObject](../../mfc/reference/coledataobject-class.md) objet est glissé sur la cible de dépôt.  
  
 [in] `dwKeyState`  
 L’état des touches de modification, qui est une combinaison au niveau du bit ou de `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, et `MK_RBUTTON`. Pour plus d’informations, consultez « Paramètres de Message » dans [sur l’entrée de souris](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 La position actuelle de la souris.  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours `DROPEFFECT_NONE`.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode avec votre implémentation personnalisée. Pour plus d’informations, consultez la [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) (méthode).  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 Affiche un menu contextuel des fenêtres à onglets, attend que l’utilisateur sélectionne un onglet et rend l’onglet sélectionné l’onglet actif.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Les coordonnées de l’emplacement où afficher le menu contextuel.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 Définit l’onglet actif d’un contrôle onglet en tant que l’onglet actif dans un groupe d’onglets interface plusieurs documents.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bActive`  
 `TRUE`Pour rendre l’onglet actuel de l’onglet actif ; `FALSE` pour désactiver l’onglet actuel.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez organiser plusieurs fenêtres de document en deux groupes d’onglets verticaux ou horizontaux et transférer aisément des documents à partir du groupe d’un onglet à l’autre.  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 Active un onglet.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iTab`  
 Spécifie l’index de base zéro de l’onglet à activer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’onglet spécifié a été activée ; `FALSE` si spécifié `iTab` la valeur du paramètre n’est pas valide.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode n’envoie pas le `AFX_WM_CHANGE_ACTIVE_TAB` notification à la fenêtre parent du contrôle d’onglet.  
  
 Le `SetActiveTab` méthode appelle automatiquement la [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) méthode pour empêcher le clignotement de l’écran.  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 Active ou désactive l’utilisation d’une police en gras dans les onglets.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsBold`  
 `TRUE`Pour utiliser une police en gras pour afficher l’étiquette de l’onglet actif ; `FALSE` permet d’afficher l’étiquette de la police standard. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 Spécifie si un rectangle de frame est dessiné autour d’une barre incorporée.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDraw`  
 `TRUE`Pour afficher un rectangle de cadre autour d’une barre incorporée ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 Spécifie s’il faut dessiner plat ou une image 3D autour de la zone de l’onglet.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bFlat`  
 `TRUE`Pour dessiner une image à deux dimensions (2D) autour de la zone de l’onglet ; `FALSE` pour dessiner un cadre (3D) en trois dimensions. La valeur par défaut est `TRUE`.  
  
 [in] `bRepaint`  
 `TRUE`redessiner la fenêtre immédiatement ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 Spécifie une liste d’images.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 L’ID d’une ressource bitmap qui contient la liste d’images.  
  
 [in] `cx`  
 La largeur de chaque image, en pixels. La valeur par défaut est 15.  
  
 [in] `clrTransp`  
 La couleur de l’image transparente. Les parties de l’image qui sont de cette couleur est transparents. La valeur par défaut est la couleur magenta, RGB(255,0,255).  
  
 [in] `hImageList`  
 Handle vers une liste d’images préchargé.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi. `FALSE`Si le contrôle d’onglet est créé à l’aide d’un style à deux dimensions ou si la première surcharge de méthode ne peut pas charger l’image bitmap spécifiée par la `uiID` paramètre.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour définir une liste d’images pour le contrôle onglet. Les images à partir de la liste d’images s’affichent en regard de l’étiquette de l’onglet. Cette méthode recalcule la hauteur de l’onglet afin que l’onglet est calibré pour contenir l’image et le texte.  
  
 Utilisez le [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) méthode est héritée par le contrôle d’onglet pour spécifier l’index de l’image à afficher.  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 Spécifie comment le contrôle onglet en cours peut être redimensionné et réaffiche ensuite le contrôle.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `resizeMode`  
 Parmi les `CMFCTabCtrl::ResizeMode` des valeurs d’énumération qui spécifie comment le contrôle onglet peut être redimensionné. Pour obtenir la liste des valeurs possibles, consultez le tableau dans la section Notes.  
  
### <a name="remarks"></a>Remarques  
 Le `resizeMode` paramètre peut prendre l’une des opérations suivantes `ResizeMode` valeurs d’énumération.  
  
|Nom|Description|  
|----------|-----------------|  
|RESIZE_NO|Impossible de redimensionner le contrôle onglet.|  
|RESIZE_VERT|Le contrôle onglet peut être redimensionné verticalement, mais non horizontalement.|  
|RESIZE_HORIZ|Le contrôle onglet peut être redimensionné horizontalement, mais non verticalement.|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 Spécifie la largeur de l’onglet maximale dans une fenêtre à onglets.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nTabMaxWidth`  
 Largeur d’onglet maximale, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette méthode permet de limiter la largeur de chaque onglet dans une fenêtre à onglets. Cette méthode est utile si les onglets ont des étiquettes très longs. Le [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) constructeur de classe initialise la largeur maximale onglet 0, ce qui signifie réellement que la largeur n’est pas limitée.  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 Met fin à l’opération en cours de redimensionnement du contrôle onglet.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bCancel`  
 `TRUE`pour abandonner l’opération de redimensionnement en cours ; `FALSE` pour effectuer les opération de redimensionnement en cours. Dans les deux cas, le framework s’arrête de dessiner le rectangle de redimensionnement.  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 Dessine une barre de défilement horizontal d’un contrôle onglet qui affiche les onglets plats.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `pScrollInfo`  
 Pointeur vers un [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) structure ou `NULL`. Lorsque cette méthode est retournée, et si ce paramètre n’est pas `NULL`, la structure contient tous les paramètres de la barre de défilement. La valeur par défaut est `NULL`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode réussit ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode affecte uniquement un contrôle onglet qui affiche les onglets plats. La barre de défilement influe sur tous les onglets en même temps.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane (classe)](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane (classe)](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl (classe)](../../mfc/reference/cmfcbasetabctrl-class.md)

