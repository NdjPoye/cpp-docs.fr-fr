---
title: Classe de CMFCColorButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton::m_Color data member
- CMFCColorButton::m_bAutoSetFocus data member
- CMFCColorButton::m_pPopup data member
- CMFCColorButton::m_nColumns data member
- CMFCColorButton class
- CMFCColorButton::m_strAutoColorText data member
- CMFCColorButton::m_bAltColorDlg data member
- CMFCColorButton::m_strDocColorsText data member
- CMFCColorButton::m_strOtherText data member
- CMFCColorButton::m_pPalette data member
- CMFCColorButton::m_lstDocColors data member
- CMFCColorButton::m_ColorAutomatic data member
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
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
ms.openlocfilehash: 6a9290d396c8ce5ccafa2ae556b21ff89806d830
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton (classe)
Le `CMFCColorButton` et [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) classes sont utilisées conjointement pour implémenter un contrôle de sélecteur de couleurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Construit un nouveau `CMFCColorButton` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Active ou désactive un bouton « automatique » qui est positionné au-dessus des boutons de couleur normal. (Le bouton automatique du système standard est intitulé **automatique**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Active ou désactive un bouton « autre » qui se trouve sous les boutons de couleur normal. (Le système standard est étiqueté « autre » bouton **couleurs supplémentaires... **.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Récupère la couleur automatique en cours.|  
|[CMFCColorButton::GetColor](#getcolor)|Récupère la couleur d’un bouton.|  
|[CMFCColorButton::SetColor](#setcolor)|Définit la couleur d’un bouton.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Définit un nom de couleur.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Définit le nombre de colonnes dans la boîte de dialogue de sélecteur de couleurs.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Spécifie une liste de couleurs de document spécifique qui sont affichés dans la boîte de dialogue de sélecteur de couleurs.|  
|[CMFCColorButton::SetPalette](#setpalette)|Spécifie une palette de couleurs d’affichage standard.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Modifie la taille du contrôle de bouton, en fonction de sa taille text et image.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Indique si le bouton de couleur actuel est affiché dans le style visuel de Windows XP.|  
|[CMFCColorButton::OnDraw](#ondraw)|Appelé par l’infrastructure pour afficher une image du bouton.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Appelé par l’infrastructure pour afficher la bordure du bouton.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Appelé par l’infrastructure pour afficher un rectangle de focus lorsque le bouton a un intérêt particulier.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Appelé par l’infrastructure lorsque la boîte de dialogue de sélecteur de couleurs est sur le point d’être affiché.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Initialise le `m_pPalette` protégé de membre de données de la palette spécifiée ou dans la palette du système par défaut.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Appelé par l’infrastructure lorsque l’utilisateur sélectionne une couleur de la palette de la boîte de dialogue de sélecteur de couleurs.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|`m_bAltColorDlg`|Valeur booléenne. Si `TRUE`, le framework affiche la [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) boîte de dialogue de couleur lorsque la *autres* bouton est activé, ou si `FALSE`, la boîte de dialogue couleur. La valeur par défaut est `TRUE`. Pour plus d’informations, consultez [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Valeur booléenne. Si `TRUE`, le framework définit le focus sur le menu couleur lorsque le menu s’affiche, ou si `FALSE`, ne change pas le focus. La valeur par défaut est `TRUE`.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Indique si le mode de personnalisation est activé pour le bouton de couleur.|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur. Affiche la couleur actuellement sélectionnée.|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur. Affiche la couleur sélectionnée par défaut.|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md) de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeurs. Contient les couleurs disponibles.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) de [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeurs. Contient les couleurs du document actif.|  
|`m_nColumns`|Entier. Contient le nombre de colonnes à afficher dans la grille de couleurs dans un menu de sélection de couleur.|  
|`m_pPalette`|Un pointeur vers un [CPalette](../../mfc/reference/cpalette-class.md). Contient les couleurs disponibles dans le menu de sélection de couleur actuel.|  
|`m_pPopup`|Un pointeur vers un [CMFCColorPopupMenu classe](../../mfc/reference/cmfccolorpopupmenu-class.md) objet. Le menu de sélection de couleur qui s’affiche lorsque vous cliquez sur le bouton de couleur.|  
|`m_strAutoColorText`|Chaîne. L’étiquette du bouton « automatique » dans un menu de sélection de couleur.|  
|`m_strDocColorsText`|Chaîne. L’étiquette du bouton dans un menu de sélection de couleur qui affiche les couleurs du document.|  
|`m_strOtherText`|Chaîne. L’étiquette du bouton « autre » dans un menu de sélection de couleur.|  
  
## <a name="remarks"></a>Notes  
 Par défaut, la `CMFCColorButton` classe se comporte comme un bouton de commande qui ouvre une boîte de dialogue de sélecteur de couleurs. La boîte de dialogue de sélecteur de couleurs contient un tableau de boutons de petite couleur et un bouton « autre » qui affiche un sélecteur de couleurs personnalisées. (Le système standard est étiqueté « autre » bouton **couleurs supplémentaires... **.) Lorsqu’un utilisateur sélectionne une nouvelle couleur, le `CMFCColorButton` objet reflète la modification et affiche la couleur sélectionnée.  
  
 Créer un contrôle de bouton de couleur directement dans votre code, ou à l’aide de la **ClassWizard** outil et un modèle de boîte de dialogue. Si vous créez un contrôle de bouton de couleur directement, ajoutez un `CMFCColorButton` à votre application et puis appelez le constructeur de la variable et `Create` méthodes de la `CMFCColorButton` objet. Si vous utilisez la **ClassWizard**, ajouter un `CButton` variable à votre application, puis modifiez le type de la variable de `CButton` à `CMFCColorButton`.  
  
 La boîte de dialogue de sélecteur de couleurs ( [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md)) est affiché par le [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) méthode lorsque l’infrastructure appelle la `OnLButtonDown` Gestionnaire d’événements. Le [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) méthode peut être substituée pour prendre en charge la sélection de couleurs personnalisées.  
  
 Le `CMFCColorButton` objet informe le parent de modification d’une couleur en lui envoyant un `WM_COMMAND | BN_CLICKED` notification. Le parent utilise la [CMFCColorButton::GetColor](#getcolor) méthode pour récupérer la couleur actuelle.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer un bouton de couleur à l’aide de différentes méthodes dans la `CMFCColorButton` classe. Les méthodes de définir la couleur du bouton couleur et le nombre de colonnes et activer automatique et les autres boutons. Cet exemple fait partie de la [exemple de démonstration de barre d’état](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#10;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#11;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 Construit un nouveau `CMFCColorButton` objet.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 Activer ou désactiver le bouton « automatique » d’un contrôle de sélecteur de couleurs et définir la couleur automatique (par défaut).  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Spécifie l’automatique texte du bouton.  
  
 [in] `colorAutomatic`  
 Une valeur RVB qui spécifie l’automatique couleur du bouton par défaut.  
  
 [in] `bEnable`  
 Spécifie si le bouton automatique est activé ou désactivé.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 Activer ou désactiver le bouton « autre » qui apparaît sous les boutons de couleur normal.  
  
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
 Spécifie si les [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) boîte de dialogue ou la boîte de dialogue couleur est ouvert lorsque l’utilisateur clique sur le bouton.  
  
 [in] `bEnable`  
 Spécifie si le bouton « autre » est activé ou désactivé.  
  
### <a name="remarks"></a>Remarques  
 Cliquez sur le bouton « autre » pour afficher une boîte de dialogue couleur. Si le *bAltColorDlg* paramètre est `TRUE`, le [CMFCColorDialog classe](../../mfc/reference/cmfccolordialog-class.md) est affichée ; sinon, la boîte de dialogue couleur s’affiche.  
  
##  <a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 Récupère la couleur actuelle du automatique (par défaut).  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur RVB représentant la couleur automatique en cours.  
  
### <a name="remarks"></a>Remarques  
 La couleur actuelle du automatique est définie par le [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) (méthode).  
  
##  <a name="getcolor"></a>CMFCColorButton::GetColor  
 Récupère la couleur actuellement sélectionnée.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur RVB.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Indique si le bouton de couleur actuel est affiché dans le style visuel de Windows XP.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les styles visuels sont pris en charge et le bouton de couleur actuelle s’affiche dans le style visuel de Windows XP ; dans le cas contraire, `FALSE`.  
  
##  <a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 Définit un bouton de couleur pour le mode de personnalisation.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Notes  
 Si vous devez ajouter un bouton de couleur pour une boîte de dialogue de personnalisation (ou autoriser l’utilisateur à effectuer une autre sélection de couleur pendant la personnalisation), activer le bouton en définissant le `m_bEnabledInCustomizeMode` membre à `TRUE`. Par défaut, ce membre est défini sur `FALSE`.  
  
##  <a name="ondraw"></a>CMFCColorButton::OnDraw  
 Appelé par l’infrastructure d’afficher une image du bouton.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointe vers le contexte de périphérique qui est utilisé pour restituer l’image du bouton.  
  
 [in] `rect`  
 Un rectangle qui délimite le bouton.  
  
 [in] `uiState`  
 Spécifie l’état visuel du bouton.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour personnaliser le processus de rendu.  
  
##  <a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 Appelé par l’infrastructure pour afficher la bordure du bouton.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointe vers le contexte de périphérique utilisé pour dessiner la bordure.  
  
 [in] `rectClient`  
 Un rectangle dans le contexte de périphérique spécifié par le le `pDC` paramètre qui définit les limites du bouton à dessiner.  
  
 [in] `uiState`  
 Spécifie l’état visuel du bouton.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour personnaliser l’apparence de bordure du bouton de couleur.  
  
##  <a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 Appelé par l’infrastructure pour afficher un rectangle de focus lorsque le bouton est activé.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointe vers le contexte de périphérique utilisé pour dessiner le rectangle de focus.  
  
 [in] `rectClient`  
 Un rectangle dans le contexte de périphérique spécifié par le `pDC` paramètre qui définit les limites du bouton.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode pour personnaliser l’apparence du rectangle de focus.  
  
##  <a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 Appelée avant que la barre de couleurs de menu contextuel s’affiche.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 Initialise le `m_pPalette` protégé de membre de données de la palette spécifiée ou dans la palette du système par défaut.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `pPal`|Un pointeur vers une palette logique ou `NULL`. Si `NULL`, la palette système par défaut est utilisée.|  
  
##  <a name="setcolor"></a>CMFCColorButton::SetColor  
 Spécifie la couleur du bouton.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 Une valeur RVB.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setcolorname"></a>CMFCColorButton::SetColorName  
 Spécifie le nom d’une couleur.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 La valeur de couleur RVB.  
  
 [in] `strName`  
 Nom de la couleur.  
  
### <a name="remarks"></a>Remarques  
 La liste des noms de couleurs est globale pour chaque application. Par conséquent, cette méthode transfère ses paramètres à [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 Définit le nombre de colonnes qui sont affichées dans le tableau de couleurs qui est présenté à l’utilisateur pendant le processus de sélection de couleur de l’utilisateur.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nColumns`  
 Spécifie le nombre de colonnes.  
  
### <a name="remarks"></a>Remarques  
 L’utilisateur peut sélectionner une couleur à partir d’une barre de couleur du menu contextuel qui affiche un tableau de couleurs prédéfinies. Utilisez cette méthode pour définir le nombre de colonnes dans la table.  
  
##  <a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 Spécifie un jeu de couleurs et le nom. Le jeu de couleurs s’affiche avec un [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) objet.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Spécifie l’étiquette à afficher avec le jeu de couleurs du document.  
  
 [in] `lstColors`  
 Une référence à une liste de valeurs RVB.  
  
### <a name="remarks"></a>Remarques  
 A `CMFCColorButton` objet conserve une liste de valeurs RVB qui sont transférés vers un [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) objet. Lorsque la barre de couleurs s’affiche, ces couleurs sont affichées dans une section spéciale dont l’étiquette est spécifiée par la `lpszLabel` paramètre.  
  
##  <a name="setpalette"></a>CMFCColorButton::SetPalette  
 Spécifie les couleurs standards à afficher dans la barre de couleur du menu contextuel.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPalette`  
 Pointeur vers une palette de couleurs.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 Redimensionne le contrôle button pour ajuster le texte et l’image.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bCalcOnly`  
 Si elle est différente de zéro, la nouvelle taille du contrôle est calculée, mais la taille réelle n’est pas modifiée.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CSize` objet qui spécifie une nouvelle taille du contrôle bouton.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 Appelé par l’infrastructure lorsque l’utilisateur sélectionne une couleur dans la barre de couleurs qui s’affiche lorsque l’utilisateur clique sur le bouton de couleur.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 Couleur sélectionnée par l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 Le `UpdateColor` fonction modifie les couleurs du bouton actuellement sélectionné et informe le parent en envoyant un `WM_COMMAND` de message avec un `BN_CLICKED` notification standard. Utilisez le [CMFCColorButton::GetColor](#getcolor) méthode pour récupérer la couleur sélectionnée.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCButton (classe)](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar (classe)](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette (classe)](../../mfc/reference/cpalette-class.md)   
 [CArray (classe)](../../mfc/reference/carray-class.md)   
 [CList (classe)](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)

