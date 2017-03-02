---
title: Classe de CMFCToolBarEditBoxButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OnDrawOnCustomizeList
- OnDraw
- CMFCToolBarEditBoxButton::OnDrawOnCustomizeList
- CMFCToolBarEditBoxButton.SetACCData
- CMFCToolBarEditBoxButton::OnDraw
- OnCalculateSize
- SetACCData
- CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton::SetACCData
- CMFCToolBarEditBoxButton::Serialize
- CMFCToolBarEditBoxButton.OnDraw
- CMFCToolBarEditBoxButton.OnDrawOnCustomizeList
- CMFCToolBarEditBoxButton::OnCalculateSize
- Serialize
- CMFCToolBarEditBoxButton.Serialize
- CMFCToolBarEditBoxButton.OnCalculateSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton class
- SetACCData method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- Serialize method
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
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
ms.openlocfilehash: 7f79c69c9f370f2d79752ed141affac3f97ce716
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton (classe)
Un bouton de barre d’outils qui contient un contrôle d’édition ( [classe CEdit](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Construit un objet `CMFCToolBarEditBoxButton`.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Spécifie si un utilisateur peut étendre le bouton pendant la personnalisation. (Substitue [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Copie les propriétés d’un autre bouton de barre d’outils sur le bouton en cours. (Substitue [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Crée un nouveau contrôle d’édition dans le bouton.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Récupère le premier `CMFCToolBarEditBoxButton` objet dans l’application ayant l’ID de commande spécifié.|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Récupère le texte du premier contrôle de barre d’outils de la zone Modifier ayant l’ID de commande spécifié.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Récupère l’ID de ressource du menu contextuel qui est associé au bouton.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Récupère le rectangle englobant de la partie de modifier l’édition du bouton de zone.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Retourne un pointeur vers le contrôle d’édition qui est incorporé dans le bouton.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Récupère le handle de fenêtre qui est associé au bouton de barre d’outils. (Substitue [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Récupère la région de la zone cliente du bouton qui doit être redessiné. (Substitue [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Détermine si une bordure du bouton s’affiche lorsqu’un utilisateur clique sur le bouton. (Substitue [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Détermine si les boutons de zone de modification ont un style à deux dimensions.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Spécifie si le bouton traite la [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message. (Substitue [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Appelé par l’infrastructure lorsque le bouton est ajouté à un **personnaliser** boîte de dialogue. (Substitue [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Appelé par l’infrastructure pour calculer la taille du bouton pour le contexte de périphérique spécifié et l’état d’ancrage. (Substitue [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Appelé par l’infrastructure lorsque le bouton est inséré dans une barre d’outils. (Substitue [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Appelé par l’infrastructure lorsque l’utilisateur clique sur le bouton de la souris. (Substitue [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Appelé par l’infrastructure lors de la barre d’outils parent gère un `WM_CTLCOLOR` message. (Substitue [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Appelée par l’infrastructure pour dessiner le bouton en utilisant les options et les styles spécifiés. (Substitue [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Appelé par l’infrastructure pour dessiner le bouton dans le **commandes** volet de la **personnaliser** boîte de dialogue. (Substitue [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Appelé par l’infrastructure lorsque la police globale a été modifiée. (Substitue [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Appelé par l’infrastructure lorsque la barre d’outils parent se déplace. (Substitue [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Appelé par l’infrastructure lorsque le bouton est visible ou invisible. (Substitue [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Appelé par l’infrastructure lors de la barre d’outils parent change sa taille ou la position et cette modification entraîne le bouton pour modifier la taille. (Substitue [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Appelé par l’infrastructure lors de la barre d’outils parent met à jour son texte d’info-bulle. (Substitue [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Lit de cet objet dans une archive ou écrit dans une archive. (Substitue [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Remplit les `CAccessibilityData` avec accessibilité des données à partir du bouton de barre d’outils. (Substitue [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContents](#setcontents)|Définit le texte du contrôle d’édition du bouton.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Recherche le bouton de contrôle d’édition qui possède un ID de commande spécifié et définit le texte dans le contrôle d’édition de ce bouton.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Spécifie l’ID de ressource du menu contextuel qui est associé au bouton.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Spécifie l’apparence de style à deux dimensions de boutons de zone de modification dans l’application.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Spécifie le style du bouton. (Substitue [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Notes  
 Pour ajouter un bouton de zone de modification à une barre d’outils, procédez comme suit :  
  
 1. Réservez un ID de ressource factice pour le bouton dans la ressource de la barre d'outils parente.  
  
 2. Construire un `CMFCToolBarEditBoxButton` objet.  
  
 3. Dans le Gestionnaire de messages qui traite le `AFX_WM_RESETTOOLBAR` du message, remplacez le bouton fictif avec le nouveau bouton de zone de liste déroulante à l’aide de [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Pour plus d’informations, consultez [procédure pas à pas : placer le contrôle sur la barre de d’outils](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCToolBarEditBoxButton` classe. L’exemple montre comment spécifier qu’un utilisateur peut étendre le bouton pendant la personnalisation, spécifier qu’une bordure du bouton s’affiche lorsqu’un utilisateur clique sur le bouton, définir le texte dans le contrôle de zone de texte, spécifier l’apparence de style à deux dimensions des boutons de zone de modification dans l’application et spécifier le style d’un contrôle de zone de modification de barre d’outils.  
  
 [!code-cpp[NVC_MFC_RibbonApp numéro&40;](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbareditboxbutton.h  
  
##  <a name="a-namecanbestretcheda--cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarEditBoxButton::CanBeStretched  
 Spécifie si un utilisateur peut étendre le bouton pendant la personnalisation.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, le framework n’autorise pas l’utilisateur d’étendre un bouton de barre d’outils pendant la personnalisation. Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) en permettant à l’utilisateur d’étendre un bouton de barre d’outils boîte modifier pendant la personnalisation.  
  
##  <a name="a-namecmfctoolbareditboxbuttona--cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 Construit un [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) objet.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 Spécifie l’ID de contrôle.  
  
 [in] `iImage`  
 Spécifie l’index de base zéro d’une image de la barre d’outils. L’image se trouve dans le [CMFCToolBarImages classe](../../mfc/reference/cmfctoolbarimages-class.md) objet [CMFCToolBar classe](../../mfc/reference/cmfctoolbar-class.md) classe conserve.  
  
 [in] `dwStyle`  
 Spécifie le style de contrôle d’édition.  
  
 [in] `iWidth`  
 Spécifie la largeur en pixels du contrôle d’édition.  
  
### <a name="remarks"></a>Notes  
 Le constructeur par défaut définit le style de contrôle d’édition à la combinaison suivante :  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 La largeur par défaut du contrôle est 150 pixels.  
  
##  <a name="a-namecopyfroma--cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarEditBoxButton::CopyFrom  
 Copie les propriétés d’un autre bouton de barre d’outils sur le bouton en cours.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `src`  
 Une référence au bouton source à partir duquel copier.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour copier un autre bouton de barre d’outils sur ce bouton de barre d’outils. `src`doit être de type `CMFCToolBarEditBoxButton`.  
  
##  <a name="a-namecreateedita--cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarEditBoxButton::CreateEdit  
 Crée un nouveau contrôle d’édition dans le bouton.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 `[in] pWndParent`  
 Spécifie la fenêtre parente du contrôle d’édition. Il ne doit pas être NULL.  
  
 `[in] rect`  
 Spécifie la taille et la position du contrôle d’édition.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le contrôle d’édition qui vient d’être créé ; Il est `NULL` cas d’échouent de la création du contrôle et les pièces jointes.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CMFCToolBarEditBoxButton`objet en deux étapes. Tout d’abord appeler le constructeur, puis appelez `CreateEdit,` qui crée le contrôle d’édition Windows et l’attache à le `CMFCToolBarEditBoxButton` objet.  
  
##  <a name="a-namegetbycmda--cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarEditBoxButton::GetByCmd  
 Récupère le premier `CMFCToolBarEditBoxButton` objet dans l’application ayant l’ID de commande spécifié.  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmd`  
 L’ID de commande du bouton à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 La première `CMFCToolBarEditBoxButton` objet dans l’application qui a l’ID de la commande spécifiée, ou `NULL` si aucun objet n’existe.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode d’utilitaire partagé est utilisée par des méthodes telles que [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) et [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) pour définir ou obtenir le texte du premier contrôle de barre d’outils de la zone Modifier ayant l’ID de commande spécifié.  
  
##  <a name="a-namegetcontentsalla--cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>CMFCToolBarEditBoxButton::GetContentsAll  
 Récupère le texte du premier contrôle de barre d’outils de la zone Modifier ayant l’ID de commande spécifié.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmd`  
 L’ID de commande du bouton à partir duquel récupérer le contenu.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` objet qui contient le texte du premier contrôle de barre d’outils de la zone Modifier ayant l’ID de commande spécifié.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne une chaîne vide si aucun `CMFCToolBarEditBoxButton` objets ont des ID de commande spécifié.  
  
##  <a name="a-namegetcontextmenuida--cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarEditBoxButton::GetContextMenuID  
 Récupère l’ID de ressource du menu contextuel qui est associé au bouton.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de ressource du menu contextuel qui est associé avec le bouton ou 0 si le bouton ne comporte aucun menu contextuel associé.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure utilise l’ID de ressource pour créer le menu contextuel lorsque l’utilisateur clique sur le bouton.  
  
##  <a name="a-namegeteditbordera--cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>CMFCToolBarEditBoxButton::GetEditBorder  
 Récupère le rectangle englobant de la partie de modifier l’édition du bouton de zone.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rectBorder`  
 Une référence à la `CRect` objet qui reçoit le rectangle englobant.  
  
### <a name="remarks"></a>Notes  
 Cette méthode récupère le rectangle englobant du contrôle d’édition dans les coordonnées clientes. Il étend la taille du rectangle dans chaque direction d’un pixel.  
  
 Le [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) méthode appelle cette méthode lorsqu’il dessine la bordure autour d’un `CMFCToolBarEditBoxButton` objet.  
  
##  <a name="a-namegeteditboxa--cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>CMFCToolBarEditBoxButton::GetEditBox  
 Retourne un pointeur vers le [classe CEdit](../../mfc/reference/cedit-class.md) contrôle qui est incorporé dans le bouton.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [classe CEdit](../../mfc/reference/cedit-class.md) contrôle qui contient le bouton. Il est `NULL` si le `CEdit` contrôle n’a pas encore été créé.  
  
### <a name="remarks"></a>Remarques  
 Vous créez le `CEdit` contrôle en appelant [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="a-namegethwnda--cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarEditBoxButton::GetHwnd  
 Récupère le handle de fenêtre qui est associé au bouton de barre d’outils.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle de fenêtre qui est associé au bouton.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode substitue la [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) méthode en retournant le handle de fenêtre de la partie du contrôle de modifier l’édition du bouton de zone.  
  
##  <a name="a-namegetinvalidaterecta--cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarEditBoxButton::GetInvalidateRect  
 Récupère la région de la zone cliente du bouton qui doit être redessiné.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CRect` objet qui spécifie la région qui doit être redessinée.  
  
### <a name="remarks"></a>Notes  
 Cette méthode étend l’implémentation de la classe de base, [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), en incluant dans la région de la zone de l’étiquette de texte.  
  
##  <a name="a-namehavehotbordera--cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarEditBoxButton::HaveHotBorder  
 Détermine si une bordure du bouton s’affiche lorsqu’un utilisateur clique sur le bouton.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si un bouton affiche sa bordure lorsque sélectionné ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode étend l’implémentation de la classe de base, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), en retournant une valeur différente de zéro si le contrôle est visible.  
  
##  <a name="a-nameisflatmodea--cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarEditBoxButton::IsFlatMode  
 Détermine si les boutons de zone de modification ont un style à deux dimensions.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les boutons ont un style à deux dimensions ; Sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, les boutons de zone de modification ont un style à deux dimensions. Utilisez le [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) méthode pour modifier l’apparence du style à deux dimensions de votre application.  
  
##  <a name="a-namenotifycommanda--cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarEditBoxButton::NotifyCommand  
 Spécifie si le bouton traite la [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iNotifyCode`  
 Le message de notification qui est associé à la commande.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le bouton traite la `WM_COMMAND` message, ou `FALSE` pour indiquer que le message doit être géré par la barre d’outils parent.  
  
### <a name="remarks"></a>Notes  
 Le framework appelle cette méthode lorsqu’il doit envoyer un [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) message de la fenêtre parente.  
  
 Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) en traitant le [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) notification. Pour chaque zone d’édition avec le même ID de commande en tant que cet objet, il définit son étiquette de texte pour l’étiquette de texte de cet objet.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Appelé par l’infrastructure lorsque le bouton est ajouté à un **personnaliser** boîte de dialogue.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) en copiant les propriétés de ce contrôle dans une barre d’outils qui a le même ID de commande en tant que cet objet. Cette méthode ne fait rien si aucune barre d’outils ne comporte un contrôle de zone de modification qui a le même ID de commande en tant que cet objet.  
  
 Pour plus d’informations sur la **personnaliser** boîte de dialogue, consultez [CMFCToolBarsCustomizeDialog classe](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Appelé par l’infrastructure lorsque le bouton est inséré dans une barre d’outils.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndParent`  
 Pointeur vers la nouvelle fenêtre parent.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode substitue l’implémentation de classe de base ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) en la recréant interne `CEdit` objet.  
  
##  <a name="a-nameonclicka--cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarEditBoxButton::OnClick  
 Appelé par l’infrastructure lorsque l’utilisateur clique sur le bouton de la souris.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Non utilisé.  
  
 [in] `bDelay`  
 Non utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton traite le message de clic ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode substitue l’implémentation de classe de base ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) en retournant une valeur différente de zéro si interne `CEdit` objet est visible.  
  
##  <a name="a-nameonctlcolora--cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarEditBoxButton::OnCtlColor  
 Appelé par l’infrastructure lors de la barre d’outils parent gère un `WM_CTLCOLOR` message.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Le contexte de périphérique qui affiche le bouton.  
  
 [in] `nCtlColor`  
 Non utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers le pinceau fenêtre global.  
  
### <a name="remarks"></a>Notes  
 Cette méthode substitue l’implémentation de classe de base ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) en définissant les couleurs de texte et d’arrière-plan du contexte de périphérique fournis globale du texte et les couleurs d’arrière-plan, respectivement.  
  
 Pour plus d’informations sur les options globales qui sont disponibles pour votre application, consultez la page [afx_global_data, Structure](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Appelé par l’infrastructure lorsque la police globale a été modifiée.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) en modifiant la police du contrôle à celle de la police globale.  
  
 Pour plus d’informations sur les options globales qui sont disponibles pour votre application, consultez la page [afx_global_data, Structure](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonmovea--cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarEditBoxButton::OnMove  
 Appelé par l’infrastructure lorsque la barre d’outils parent se déplace.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode substitue l’implémentation de classe par défaut ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) en mettant à jour la position de l’élément interne `CEdit` objet  
  
##  <a name="a-nameonshowa--cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarEditBoxButton::OnShow  
 Appelé par l’infrastructure lorsque le bouton est visible ou invisible.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 Spécifie si le bouton est visible. Si ce paramètre est `TRUE`, le bouton est visible. Dans le cas contraire, le bouton n’est pas visible.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) en affichant le bouton si `bShow` est `TRUE`. Sinon, cette méthode masque le bouton.  
  
##  <a name="a-nameonsizea--cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarEditBoxButton::OnSize  
 Appelé par l’infrastructure lors de la barre d’outils parent change sa taille ou la position et cette modification entraîne le bouton pour modifier la taille.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iSize`  
 La nouvelle largeur du bouton, en pixels.  
  
### <a name="remarks"></a>Notes  
 Cette méthode substitue l’implémentation de classe par défaut, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), en mettant à jour la taille et la position d’interne `CEdit` objet.  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Appelé par l’infrastructure lors de la barre d’outils parent met à jour son texte d’info-bulle.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndParent`  
 Non utilisé.  
  
 [in] `iButtonIndex`  
 Non utilisé.  
  
 [in] `wndToolTip`  
 Contrôle qui affiche le texte d’info-bulle.  
  
 [out] `str`  
 Un `CString` objet qui reçoit le texte d’info-bulle mis à jour.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode met à jour le texte d’info-bulle ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette méthode étend l’implémentation de classe de base ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) en affichant le texte d’info-bulle associé à la partie d’édition du bouton. Si le texte interne `CEdit` objet est `NULL` ou le handle de fenêtre de la `CEdit` objet n’identifie pas une fenêtre existante, cette méthode ne fait rien et retourne `FALSE`.  
  
##  <a name="a-namesetcontentsa--cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>CMFCToolBarEditBoxButton::SetContents  
 Définit le texte dans le contrôle de zone de texte.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Paramètres  
 `[in] sContents`  
 Spécifie le texte à définir.  
  
##  <a name="a-namesetcontentsalla--cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>CMFCToolBarEditBoxButton::SetContentsAll  
 Recherche un [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) objet qui possède un ID de commande spécifié et définit le texte spécifié dans sa zone de texte.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmd`  
 Spécifie l’ID de commande du contrôle pour lequel le texte sera modifié.  
  
 [in] `strContents`  
 Spécifie le texte à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le texte a été défini ; 0 si la `CMFCToolBarEditBoxButton` contrôle avec l’ID de commande spécifié n’existe pas.  
  
##  <a name="a-namesetcontextmenuida--cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarEditBoxButton::SetContextMenuID  
 Spécifie l’ID de ressource du menu contextuel qui est associé au bouton.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmd`  
 L’ID de ressource du menu contextuel.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure utilise l’ID de ressource pour créer le menu contextuel lorsque l’utilisateur clique sur le bouton de barre d’outils.  
  
##  <a name="a-namesetflatmodea--cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarEditBoxButton::SetFlatMode  
 Spécifie l’apparence de style à deux dimensions de boutons de zone de modification dans l’application.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bFlat`  
 Le style à deux dimensions pour modifier les boutons de zone. Si ce paramètre est `TRUE`, l’apparence du style à deux dimensions est activée ; sinon, l’apparence du style à deux dimensions est désactivée.  
  
### <a name="remarks"></a>Remarques  
 Le style à deux dimensions par défaut pour modifier les boutons de zone est `TRUE`. Utilisez le [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) méthode pour récupérer l’apparence du style à deux dimensions de votre application.  
  
##  <a name="a-namesetstylea--cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarEditBoxButton::SetStyle  
 Spécifie le style d’une barre d’outils de contrôle zone d’édition.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nStyle`  
 Un nouveau style à définir.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode définit [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) à `nStyle` il désactive également la zone de texte lorsque l’application est en mode de personnalisation et l’active lorsque l’application n’est pas en mode de personnalisation (voir [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) et [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Consultez la page [les Styles de contrôle de barre d’outils](../../mfc/reference/toolbar-control-styles.md) pour obtenir la liste des indicateurs de style valide.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton (classe)](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Classe CEdit](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Procédure pas à pas : Placement de contrôles dans les barres d’outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)




