---
title: Classe de CMFCColorMenuButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorMenuButton class
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
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
ms.openlocfilehash: a9b1e7a3dbfe4d98b3d51850723eb22ec1f9da06
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton (classe)
La `CMFCColorMenuButton` classe prend en charge une commande de menu ou un bouton de barre d’outils qui démarre une boîte de dialogue de sélecteur de couleurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Construit un objet `CMFCColorMenuButton`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Active ou désactive un bouton « automatique » qui est positionné au-dessus des boutons de couleur normal. (Le bouton automatique du système standard est intitulé **automatique**.)|  
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Permet d’afficher les couleurs de document spécifique au lieu de couleurs système.|  
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Active ou désactive un bouton « autre » qui se trouve sous les boutons de couleur normal. (Le système standard est étiqueté « autre » bouton **couleurs supplémentaires... **.)|  
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Permet de détacher un volet de couleur.|  
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Récupère la couleur automatique en cours.|  
|[CMFCColorMenuButton::GetColor](#getcolor)|Récupère la couleur du bouton de l’actuelle.|  
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Récupère la couleur qui correspond à un ID de commande spécifié.|  
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Appelé par l’infrastructure lorsque la fenêtre parente change.|  
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Ouvre une boîte de dialogue de sélection de couleur.|  
|[CMFCColorMenuButton::SetColor](#setcolor)|Définit la couleur du bouton de couleur actuel.|  
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Définit la couleur du bouton menu couleur spécifiée.|  
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Définit un nouveau nom pour la couleur spécifiée.|  
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Définit le nombre de colonnes qui sont affichées par un `CMFCColorBar` objet.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Copie un autre bouton de barre d’outils sur le bouton en cours.|  
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Crée une boîte de dialogue de sélecteur de couleurs.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Indique si les menus vides sont prises en charge.|  
|[CMFCColorMenuButton::OnDraw](#ondraw)|Appelé par l’infrastructure pour afficher une image sur un bouton.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Appelé par l’infrastructure avant une `CMFCColorMenuButton` objet est affiché dans la liste d’une boîte de dialogue de personnalisation de barre d’outils.|  
  
## <a name="remarks"></a>Notes  
 Pour remplacer le bouton de barre d’outils ou la commande de menu d’origine avec une `CMFCColorMenuButton` d’objet, de créer le `CMFCColorMenuButton` objet, la valeur appropriée de tous les [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) styles, puis appelez le `ReplaceButton` procédé de la [CMFCToolBar classe](../../mfc/reference/cmfctoolbar-class.md) classe. Si vous personnalisez une barre d’outils, appelez le [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) (méthode).  
  
 La boîte de dialogue de sélecteur de couleurs est créée lors du traitement de la [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) Gestionnaire d’événements. Le Gestionnaire d’événements informe le frame parent avec un `WM_COMMAND` message. Le `CMFCColorMenuButton` objet envoie l’ID du contrôle qui est affectée au bouton de barre d’outils ou la commande de menu d’origine.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment créer et configurer un bouton de menu de couleur à l’aide de différentes méthodes dans la `CMFCColorMenuButton` classe. Dans l’exemple, un `CPalette` objet est d’abord créé et ensuite utilisé pour construire un objet de la `CMFCColorMenuButton` classe. Le `CMFCColorMenuButton` objet est ensuite configuré en activant automatiquement et autres boutons et en définissant la couleur et le nombre de colonnes. Ce code fait partie de la [exemple du bloc-notes](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad n °&5;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_WordPad n °&6;](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcolormenubutton.h  
  
##  <a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton  
 Construit un objet `CMFCColorMenuButton`.  
  
```  
CMFCColorMenuButton();

 
CMFCColorMenuButton(
    UINT uiCmdID,  
    LPCTSTR lpszText,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Un ID de commande de bouton.  
  
 [in] `lpszText`  
 Le texte du bouton.  
  
 [in] `pPalette`  
 Pointeur vers la palette de couleurs du bouton.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur est le constructeur par défaut. Couleur actuelle de l’objet et automatique sont initialisés sur noir (RGB (0, 0, 0)).  
  
 Le deuxième constructeur initialise le bouton de la couleur qui correspond à l’ID de commande spécifié.  
  
##  <a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom  
 Une copie [CMFCToolBarMenuButton classe](../../mfc/reference/cmfctoolbarmenubutton-class.md)-objet dérivé à l’autre.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `src`  
 Bouton de la source à copier.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour copier les objets qui sont dérivées de la `CMFCColorMenuButton` objet.  
  
##  <a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu  
 Crée une boîte de dialogue de sélecteur de couleurs.  
  
```  
virtual CMFCPopupMenu* CreatePopupMenu();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet qui représente une boîte de dialogue de sélecteur de couleurs.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est appelée par l’infrastructure lorsque l’utilisateur appuie sur un bouton de menu couleur.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton  
 Active ou désactive un bouton « automatique » qui est positionné au-dessus des boutons de couleur normal. (Le bouton automatique du système standard est intitulé **automatique**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Spécifie le texte du bouton qui s’affiche lorsque le bouton est automatique.  
  
 [in] `colorAutomatic`  
 Spécifie une nouvelle couleur automatique.  
  
 [in] `bEnable`  
 Spécifie si le bouton est automatique ou non.  
  
### <a name="remarks"></a>Remarques  
 Le bouton automatique applique la couleur par défaut en cours.  
  
##  <a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors  
 Permet d’afficher les couleurs de document spécifique au lieu de couleurs système.  
  
```  
void EnableDocumentColors(
    LPCTSTR lpszLabel,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Spécifie le texte du bouton.  
  
 [in] `bEnable`  
 `TRUE`Pour afficher les couleurs de document spécifique ou `FALSE` pour afficher les couleurs système.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour afficher les couleurs du document actif ou la palette de couleurs système lorsque l’utilisateur clique sur un bouton de menu couleur.  
  
##  <a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton  
 Active ou désactive un bouton « autre » qui se trouve sous les boutons de couleur normal. (Le système standard est étiqueté « autre » bouton **couleurs supplémentaires... **.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Spécifie le texte du bouton.  
  
 [in] `bAltColorDlg`  
 Spécifier `TRUE` pour afficher les `CMFCColorDialog` boîte de dialogue, ou `FALSE` pour afficher la boîte de dialogue couleur système standard.  
  
 [in] `bEnable`  
 Spécifier `TRUE` pour afficher le bouton « autre » ; sinon, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff  
 Permet de détacher un volet de couleur.  
  
```  
void EnableTearOff(
    UINT uiID,  
    int nVertDockColumns=-1,  
    int nHorzDockRows=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 Spécifie l’ID du volet détachables.  
  
 [in] `nVertDockColumns`  
 Spécifie le nombre de colonnes dans le volet couleur verticalement ancré dans son état.  
  
 [in] `nHorzDockRows`  
 Spécifie le nombre de lignes du volet couleur ancré horizontalement dans son état.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour activer la fonctionnalité « détacher » pour le volet de couleur qui s’affiche lorsque la `CMFCColorMenuButton` appuyé.  
  
##  <a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor  
 Récupère la couleur automatique en cours.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de couleur RVB qui représente la couleur automatique en cours.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour obtenir la couleur automatique est définie par [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).  
  
##  <a name="getcolor"></a>CMFCColorMenuButton::GetColor  
 Récupère la couleur du bouton de l’actuelle.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La couleur du bouton.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID  
 Récupère la couleur qui correspond à un ID de commande spécifié.  
  
```  
static COLORREF GetColorByCmdID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Un ID de commande.  
  
### <a name="return-value"></a>Valeur de retour  
 La couleur qui correspond à l’ID de commande spécifié.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode lorsque vous avez plusieurs boutons de couleur dans une application. Lorsque l’utilisateur clique sur un bouton de couleur, le bouton envoie son ID de commande un `WM_COMMAND` message à son parent. Le `GetColorByCmdID` méthode utilise l’ID de commande pour récupérer la couleur correspondante.  
  
##  <a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsEmptyMenuAllowed  
 Indique si les menus vides sont prises en charge.  
  
```  
virtual BOOL IsEmptyMenuAllowed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les menus vides sont autorisées ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Menus vides sont prises en charge par défaut. Substituez cette méthode pour modifier ce comportement dans une classe dérivée.  
  
##  <a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd  
 Appelé par l’infrastructure lorsque la fenêtre parente change.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndParent`  
 Pointeur vers la nouvelle fenêtre parent.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="ondraw"></a>CMFCColorMenuButton::OnDraw  
 Appelé par l’infrastructure pour afficher une image sur un bouton.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Un rectangle qui délimite la zone à redessiner.  
  
 [in] `pImages`  
 Pointe vers une liste d’images de barre d’outils.  
  
 [in] `bHorz`  
 `TRUE`Pour spécifier que la barre d’outils est dans un état d’ancrage horizontal ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
 [in] `bCustomizeMode`  
 `TRUE`Pour spécifier que l’application est en mode de personnalisation ; dans le cas contraire, `FALSE`. La valeur par défaut est `FALSE`.  
  
 [in] `bHighlight`  
 `TRUE`Pour spécifier que le bouton est mis en surbrillance ; dans le cas contraire, `FALSE`. La valeur par défaut est `FALSE`.  
  
 [in] `bDrawBorder`  
 `TRUE`Pour spécifier que la bordure du bouton s’affiche ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
 [in] `bGrayDisabledButtons`  
 `TRUE`Pour spécifier que désactivé boutons sont estompées (grisée) dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList  
 Appelé par l’infrastructure avant une `CMFCColorMenuButton` objet est affiché dans la liste d’une boîte de dialogue de personnalisation de barre d’outils.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Un rectangle qui délimite le bouton à dessiner.  
  
 [in] `bSelected`  
 `TRUE`Spécifie que le bouton est dans l’état sélectionné ; dans le cas contraire, `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur du bouton.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est appelée par l’infrastructure lorsqu’un `CMFCColorMenuButton` objet est affiché dans la zone de liste au cours du processus de personnalisation de barre d’outils.  
  
##  <a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorDialog  
 Ouvre une boîte de dialogue de sélection de couleur.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `colorDefault`  
 La couleur par défaut qui est sélectionnée dans la boîte de dialogue couleur.  
  
 [out] `colorRes`  
 Retourne la couleur que l’utilisateur sélectionne dans la boîte de dialogue couleur.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur sélectionne une nouvelle couleur ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Lorsque l’utilisateur clique sur le bouton de menu, appelez cette méthode pour ouvrir une boîte de dialogue couleur. Si la valeur de retour est différent de zéro, la couleur sélectionnées par l’utilisateur est stockée dans le `colorRes` paramètre. Utilisez le [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) méthode pour basculer entre la boîte de dialogue couleurs standard et le [CMFCColorDialog classe](../../mfc/reference/cmfccolordialog-class.md) boîte de dialogue.  
  
##  <a name="setcolor"></a>CMFCColorMenuButton::SetColor  
 Définit la couleur du bouton de couleur actuel.  
  
```  
virtual void SetColor(
    COLORREF clr,  
    BOOL bNotify=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `clr`  
 Une valeur de couleur RVB.  
  
 [in] `bNotify`  
 `TRUE`Pour appliquer les `clr` couleur de paramètre à n’importe quel bouton de menu correspondant ou d’un bouton de barre d’outils ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour modifier la couleur du bouton de couleur actuel. Si le `bNotify` le paramètre est différent de zéro, la couleur du bouton correspondant sur n’importe quel menu contextuel associé ou de la barre d’outils est remplacée par la couleur spécifiée par la `clr` paramètre.  
  
##  <a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID  
 Définit la couleur du bouton menu couleur spécifiée.  
  
```  
static void SetColorByCmdID(
    UINT uiCmdID,  
    COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 L’ID de ressource d’un bouton de menu de couleur.  
  
 [in] `color`  
 Une valeur de couleur RVB.  
  
##  <a name="setcolorname"></a>CMFCColorMenuButton::SetColorName  
 Définit un nouveau nom pour la couleur spécifiée.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 La valeur RVB de la couleur dont le nom change.  
  
 [in] `strName`  
 Le nouveau nom de la couleur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsNumber  
 Définit le nombre de colonnes à afficher dans un contrôle de sélection de couleur ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) objet).  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nColumns`  
 Le nombre de colonnes à afficher.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar (classe)](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog (classe)](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton (classe)](../../mfc/reference/cmfccolorbutton-class.md)

