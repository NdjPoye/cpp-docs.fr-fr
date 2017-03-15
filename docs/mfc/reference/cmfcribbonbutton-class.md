---
title: Classe de CMFCRibbonButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButton class
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
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
ms.openlocfilehash: 08672f10cf67a773f2af8d12130c4e3f5b497e11
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbutton-class"></a>CMFCRibbonButton (classe)
La classe `CMFCRibbonButton` implémente des boutons que vous pouvez placer sur des éléments de barre de ruban, tels que les volets, les barres d'outils Accès rapide et les menus contextuels.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonButton::CMFCRibbonButton](#cmfcribbonbutton)|Construit un objet bouton de ruban.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonButton::AddSubItem](#addsubitem)|Ajoute un élément de menu au menu contextuel associé au bouton.|  
|[CMFCRibbonButton::CanBeStretched](#canbestretched)|(Substitue [CMFCRibbonBaseElement::CanBeStretched](../../mfc/reference/cmfcribbonbaseelement-class.md#canbestretched).)|  
|[CMFCRibbonButton::CleanUpSizes](#cleanupsizes)|(Substitue [CMFCRibbonBaseElement::CleanUpSizes](../../mfc/reference/cmfcribbonbaseelement-class.md#cleanupsizes).)|  
|[CMFCRibbonButton::ClosePopupMenu](#closepopupmenu)|(Substitue [CMFCRibbonBaseElement::ClosePopupMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#closepopupmenu).)|  
|[CMFCRibbonButton::DrawBottomText](#drawbottomtext)||  
|[CMFCRibbonButton::DrawImage](#drawimage)|(Substitue [CMFCRibbonBaseElement::DrawImage](../../mfc/reference/cmfcribbonbaseelement-class.md#drawimage).)|  
|[CMFCRibbonButton::DrawRibbonText](#drawribbontext)||  
|[CMFCRibbonButton::FindSubItemIndexByID](#findsubitemindexbyid)|Retourne l'index d'un élément de menu contextuel associé à l'ID de commande spécifié.|  
|[CMFCRibbonButton::GetCommandRect](#getcommandrect)||  
|[CMFCRibbonButton::GetCompactSize](#getcompactsize)|Retourne la taille réduite de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::GetCompactSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getcompactsize).)|  
|[CMFCRibbonButton::GetIcon](#geticon)||  
|[CMFCRibbonButton::GetImageIndex](#getimageindex)|Retourne l'index de l'image associée au bouton.|  
|[CMFCRibbonButton::GetImageSize](#getimagesize)|Retourne la taille d'image de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButton::GetIntermediateSize](#getintermediatesize)|Retourne la taille de l'élément de ruban dans son état intermédiaire. (Substitue [CMFCRibbonBaseElement::GetIntermediateSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getintermediatesize).)|  
|[CMFCRibbonButton::GetMenu](#getmenu)|Retourne un handle de menu Windows affecté au bouton du ruban.|  
|[CMFCRibbonButton::GetMenuRect](#getmenurect)||  
|[CMFCRibbonButton::GetRegularSize](#getregularsize)|Retourne la taille normale de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButton::GetSubItems](#getsubitems)||  
|[CMFCRibbonButton::GetTextRowHeight](#gettextrowheight)||  
|[CMFCRibbonButton::GetToolTipText](#gettooltiptext)|Retourne le texte d'info-bulle de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::GetToolTipText](../../mfc/reference/cmfcribbonbaseelement-class.md#gettooltiptext).)|  
|[CMFCRibbonButton::HasCompactMode](#hascompactmode)|Précise si l'élément de ruban a un mode réduit. (Substitue [CMFCRibbonBaseElement::HasCompactMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hascompactmode).)|  
|[CMFCRibbonButton::HasIntermediateMode](#hasintermediatemode)|Précise si l'élément de ruban a un mode intermédiaire. (Substitue [CMFCRibbonBaseElement::HasIntermediateMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hasintermediatemode).)|  
|[CMFCRibbonButton::HasLargeMode](#haslargemode)|Détermine si l'élément de ruban a un mode grand. (Substitue [CMFCRibbonBaseElement::HasLargeMode](../../mfc/reference/cmfcribbonbaseelement-class.md#haslargemode).)|  
|[CMFCRibbonButton::HasMenu](#hasmenu)|(Substitue [CMFCRibbonBaseElement::HasMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#hasmenu).)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](#isalwaysdrawborder)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](#isalwayslargeimage)|(Substitue [CMFCRibbonBaseElement::IsAlwaysLargeImage](../../mfc/reference/cmfcribbonbaseelement-class.md#isalwayslargeimage).)|  
|[CMFCRibbonButton::IsApplicationButton](#isapplicationbutton)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](#iscommandareahighlighted)||  
|[CMFCRibbonButton::IsDefaultCommand](#isdefaultcommand)|Détermine si vous avez activé la commande par défaut pour un bouton du ruban.|  
|[CMFCRibbonButton::IsDefaultPanelButton](#isdefaultpanelbutton)||  
|[CMFCRibbonButton::IsDrawTooltipImage](#isdrawtooltipimage)||  
|[CMFCRibbonButton::IsLargeImage](#islargeimage)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](#ismenuareahighlighted)||  
|[CMFCRibbonButton::IsMenuOnBottom](#ismenuonbottom)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](#ispopupdefaultmenulook)||  
|[CMFCRibbonButton::IsRightAlignMenu](#isrightalignmenu)|Détermine si le menu est aligné à droite.|  
|[CMFCRibbonButton::IsSingleLineText](#issinglelinetext)||  
|[CMFCRibbonButton::OnCalcTextSize](#oncalctextsize)|(Substitue [CMFCRibbonBaseElement::OnCalcTextSize](../../mfc/reference/cmfcribbonbaseelement-class.md#oncalctextsize).)|  
|[CMFCRibbonButton::OnDrawBorder](#ondrawborder)||  
|[CMFCRibbonButton::OnDraw](#ondraw)|Appelé par l'infrastructure pour dessiner l'élément de ruban. (Substitue [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonButton::OnFillBackground](#onfillbackground)||  
|[CMFCRibbonButton::RemoveAllSubItems](#removeallsubitems)|Supprime tous les éléments de menu du menu contextuel.|  
|[CMFCRibbonButton::RemoveSubItem](#removesubitem)|Supprime un élément de menu du menu contextuel.|  
|[CMFCRibbonButton::SetACCData](#setaccdata)|(Substitue [CMFCRibbonBaseElement::SetACCData](../../mfc/reference/cmfcribbonbaseelement-class.md#setaccdata).)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](#setalwayslargeimage)|Précise si le bouton affiche une image grande ou petite quand l‘utilisateur réduit le bouton.|  
|[CMFCRibbonButton::SetDefaultCommand](#setdefaultcommand)|Active la commande par défaut pour le bouton du ruban.|  
|[CMFCRibbonButton::SetDescription](#setdescription)|Définit la description de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::SetDescription](../../mfc/reference/cmfcribbonbaseelement-class.md#setdescription).)|  
|[CMFCRibbonButton::SetImageIndex](#setimageindex)|Affecte un index à l'image du bouton.|  
|[CMFCRibbonButton::SetMenu](#setmenu)|Affecte un menu contextuel au bouton du ruban.|  
|[CMFCRibbonButton::SetParentCategory](#setparentcategory)|(Substitue [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
|[CMFCRibbonButton::SetRightAlignMenu](#setrightalignmenu)|Aligne le menu contextuel à droite du bouton.|  
|[CMFCRibbonButton::SetText](#settext)|Définit le texte de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::SetText](../../mfc/reference/cmfcribbonbaseelement-class.md#settext).)|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonButton::OnClick](#onclick)|Appelé par l'infrastructure quand l'utilisateur clique sur le bouton.|  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser les différentes méthodes de la classe `CMFCRibbonButton`. Il montre comment construire un objet de la classe `CMFCRibbonButton`, affecter un menu contextuel au bouton du ruban, définir la description du bouton, supprimer un élément de menu du menu contextuel et aligner le menu contextuel à droite par rapport au bord du bouton.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_1.cpp)]  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser un bouton de ruban dans une application, construisez l’objet bouton et ajoutez-le au ruban approprié [panneau](../../mfc/reference/cmfcribbonpanel-class.md).  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"), // Panel name  
    m_PanelIcons.ExtractIcon (0)); // Panel icon  

// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton = 
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);

// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);

// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));
```  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonbutton.h  
  
##  <a name="a-nameaddsubitema--cmfcribbonbuttonaddsubitem"></a><a name="addsubitem"></a>CMFCRibbonButton::AddSubItem  
 Ajoute un élément de menu au menu contextuel associé au bouton.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pSubItem`  
 Spécifie un pointeur vers le nouvel élément à ajouter.  
  
 [in] `nIndex`  
 Spécifie l’index au niveau duquel ajouter l’élément dans le tableau des éléments de menu du bouton ; -1 pour ajouter l’élément à la fin du tableau d’éléments de menu.  
  
##  <a name="a-namecanbestretcheda--cmfcribbonbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCRibbonButton::CanBeStretched  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecleanupsizesa--cmfcribbonbuttoncleanupsizes"></a><a name="cleanupsizes"></a>CMFCRibbonButton::CleanUpSizes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameclosepopupmenua--cmfcribbonbuttonclosepopupmenu"></a><a name="closepopupmenu"></a>CMFCRibbonButton::ClosePopupMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecmfcribbonbuttona--cmfcribbonbuttoncmfcribbonbutton"></a><a name="cmfcribbonbutton"></a>CMFCRibbonButton::CMFCRibbonButton  
 Construit un objet bouton de ruban.  
  
```  
CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1,  
    BOOL bAlwaysShowDescription=FALSE);

CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon,  
    BOOL bAlwaysShowDescription=FALSE,  
    HICON hIconSmall=NULL,  
    BOOL bAutoDestroyIcon=FALSE,  
    BOOL bAlphaBlendIcon=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 Spécifie l’ID de commande du bouton.  
  
 [in] `lpszText`  
 Spécifie l’étiquette de texte du bouton.  
  
 [in] `nSmallImageIndex`  
 Spécifie un index de base zéro de l’image du bouton petit dans la liste d’images de la catégorie parente.  
  
 [in] `nLargeImageIndex`  
 Spécifie un index de base zéro de l’image du bouton volumineux dans la liste d’images de la catégorie parente.  
  
 [in] `hIcon`  
 Spécifie un handle de l’icône de l’application utilise l’image du bouton.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCRibbonButton` objet.  
  
 [!code-cpp[NVC_MFC_RibbonApp n °&6;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_2.cpp)]  
  
##  <a name="a-namedrawbottomtexta--cmfcribbonbuttondrawbottomtext"></a><a name="drawbottomtext"></a>CMFCRibbonButton::DrawBottomText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CSize DrawBottomText(
    CDC* pDC,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namedrawimagea--cmfcribbonbuttondrawimage"></a><a name="drawimage"></a>CMFCRibbonButton::DrawImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 [in] `type`  
 [in] `rectImage`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namedrawribbontexta--cmfcribbonbuttondrawribbontext"></a><a name="drawribbontext"></a>CMFCRibbonButton::DrawRibbonText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int DrawRibbonText(
    CDC* pDC,  
    const CString& strText,  
    CRect rectText,  
    UINT uiDTFlags,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 [in] `strText`  
 [in] `rectText`  
 [in] `uiDTFlags`  
 [in] `clrText`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namefindsubitemindexbyida--cmfcribbonbuttonfindsubitemindexbyid"></a><a name="findsubitemindexbyid"></a>CMFCRibbonButton::FindSubItemIndexByID  
 Retourne l'index d'un élément de menu contextuel associé à l'ID de commande spécifié.  
  
```  
int FindSubItemIndexByID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiID`  
 Spécifie l’ID de commande de l’élément de menu contextuel.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément secondaire qui est associé à le `uiID`. -1 s’il n’existe aucun de ces éléments secondaires.  
  
##  <a name="a-namegetcommandrecta--cmfcribbonbuttongetcommandrect"></a><a name="getcommandrect"></a>CMFCRibbonButton::GetCommandRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetCommandRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetcompactsizea--cmfcribbonbuttongetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonButton::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegeticona--cmfcribbonbuttongeticon"></a><a name="geticon"></a>CMFCRibbonButton::GetIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HICON GetIcon(BOOL bLargeIcon = TRUE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bLargeIcon`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetimageindexa--cmfcribbonbuttongetimageindex"></a><a name="getimageindex"></a>CMFCRibbonButton::GetImageIndex  
 Retourne l'index de l'image associée au bouton.  
  
```  
int GetImageIndex(BOOL bLargeImage) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bLargeImage`  
 Si `TRUE`, retourne l’index d’image dans la liste d’images qui contient les images de grande taille ; sinon, retourne l’index d’image dans la liste d’images qui contient les petites images.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de l’image du bouton dans la liste d’images associée.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbuttongetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButton::GetImageSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetImageSize(RibbonImageType type) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `type`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetintermediatesizea--cmfcribbonbuttongetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonButton::GetIntermediateSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetmenua--cmfcribbonbuttongetmenu"></a><a name="getmenu"></a>CMFCRibbonButton::GetMenu  
 Retourne un handle de menu Windows affecté au bouton du ruban.  
  
```  
HMENU GetMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle à un menu Windows associée au bouton ; `NULL` s’il n’existe aucun menu assigné.  
  
##  <a name="a-namegetmenurecta--cmfcribbonbuttongetmenurect"></a><a name="getmenurect"></a>CMFCRibbonButton::GetMenuRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetMenuRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetregularsizea--cmfcribbonbuttongetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButton::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetsubitemsa--cmfcribbonbuttongetsubitems"></a><a name="getsubitems"></a>CMFCRibbonButton::GetSubItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& GetSubItems() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegettextrowheighta--cmfcribbonbuttongettextrowheight"></a><a name="gettextrowheight"></a>CMFCRibbonButton::GetTextRowHeight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetTextRowHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegettooltiptexta--cmfcribbonbuttongettooltiptext"></a><a name="gettooltiptext"></a>CMFCRibbonButton::GetToolTipText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namehascompactmodea--cmfcribbonbuttonhascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonButton::HasCompactMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namehasintermediatemodea--cmfcribbonbuttonhasintermediatemode"></a><a name="hasintermediatemode"></a>CMFCRibbonButton::HasIntermediateMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehaslargemodea--cmfcribbonbuttonhaslargemode"></a><a name="haslargemode"></a>CMFCRibbonButton::HasLargeMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehasmenua--cmfcribbonbuttonhasmenu"></a><a name="hasmenu"></a>CMFCRibbonButton::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisalwaysdrawbordera--cmfcribbonbuttonisalwaysdrawborder"></a><a name="isalwaysdrawborder"></a>CMFCRibbonButton::IsAlwaysDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysDrawBorder() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisalwayslargeimagea--cmfcribbonbuttonisalwayslargeimage"></a><a name="isalwayslargeimage"></a>CMFCRibbonButton::IsAlwaysLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisapplicationbuttona--cmfcribbonbuttonisapplicationbutton"></a><a name="isapplicationbutton"></a>CMFCRibbonButton::IsApplicationButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsApplicationButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameiscommandareahighlighteda--cmfcribbonbuttoniscommandareahighlighted"></a><a name="iscommandareahighlighted"></a>CMFCRibbonButton::IsCommandAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsCommandAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisdefaultcommanda--cmfcribbonbuttonisdefaultcommand"></a><a name="isdefaultcommand"></a>CMFCRibbonButton::IsDefaultCommand  
 Spécifie si la commande par défaut pour un bouton de ruban est activée.  
  
```  
BOOL IsDefaultCommand() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si vous avez activé la commande par défaut pour un bouton de ruban ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameisdefaultpanelbuttona--cmfcribbonbuttonisdefaultpanelbutton"></a><a name="isdefaultpanelbutton"></a>CMFCRibbonButton::IsDefaultPanelButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDefaultPanelButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisdrawtooltipimagea--cmfcribbonbuttonisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonButton::IsDrawTooltipImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameislargeimagea--cmfcribbonbuttonislargeimage"></a><a name="islargeimage"></a>CMFCRibbonButton::IsLargeImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsLargeImage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameismenuareahighlighteda--cmfcribbonbuttonismenuareahighlighted"></a><a name="ismenuareahighlighted"></a>CMFCRibbonButton::IsMenuAreaHighlighted  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsMenuAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameismenuonbottoma--cmfcribbonbuttonismenuonbottom"></a><a name="ismenuonbottom"></a>CMFCRibbonButton::IsMenuOnBottom  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuOnBottom() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameispopupdefaultmenulooka--cmfcribbonbuttonispopupdefaultmenulook"></a><a name="ispopupdefaultmenulook"></a>CMFCRibbonButton::IsPopupDefaultMenuLook  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsPopupDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisrightalignmenua--cmfcribbonbuttonisrightalignmenu"></a><a name="isrightalignmenu"></a>CMFCRibbonButton::IsRightAlignMenu  
 Spécifie si le menu est aligné à droite.  
  
```  
BOOL IsRightAlignMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le menu est aligné à droite ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameissinglelinetexta--cmfcribbonbuttonissinglelinetext"></a><a name="issinglelinetext"></a>CMFCRibbonButton::IsSingleLineText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsSingleLineText() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameoncalctextsizea--cmfcribbonbuttononcalctextsize"></a><a name="oncalctextsize"></a>CMFCRibbonButton::OnCalcTextSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonclicka--cmfcribbonbuttononclick"></a><a name="onclick"></a>CMFCRibbonButton::OnClick  
 Appelé par l'infrastructure quand l'utilisateur clique sur le bouton.  
  
```  
virtual void OnClick(CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Spécifie la position de la souris.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode dans une classe dérivée si vous souhaitez gérer cet événement.  
  
##  <a name="a-nameondrawa--cmfcribbonbuttonondraw"></a><a name="ondraw"></a>CMFCRibbonButton::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondrawbordera--cmfcribbonbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCRibbonButton::OnDrawBorder  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonfillbackgrounda--cmfcribbonbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCRibbonButton::OnFillBackground  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameremoveallsubitemsa--cmfcribbonbuttonremoveallsubitems"></a><a name="removeallsubitems"></a>CMFCRibbonButton::RemoveAllSubItems  
 Supprime tous les éléments de menu du menu contextuel.  
  
```  
void RemoveAllSubItems();
```  
  
##  <a name="a-nameremovesubitema--cmfcribbonbuttonremovesubitem"></a><a name="removesubitem"></a>CMFCRibbonButton::RemoveSubItem  
 Supprime un élément de menu du menu contextuel.  
  
```  
BOOL RemoveSubItem(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro de l’élément de menu que vous souhaitez supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément spécifié a été supprimé avec succès ; dans le cas contraire `FALSE` si `nIndex` est un nombre négatif ou est supérieur au nombre d’éléments de menu dans le menu contextuel.  
  
##  <a name="a-namesetaccdataa--cmfcribbonbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonButton::SetACCData  
 Définit les données d’accessibilité du bouton de ruban.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pParent`  
 La fenêtre parente de l’élément ruban.  
  
 `data`  
 Les données d’accessibilité de l’élément ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` en cas de réussite, sinon FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetalwayslargeimagea--cmfcribbonbuttonsetalwayslargeimage"></a><a name="setalwayslargeimage"></a>CMFCRibbonButton::SetAlwaysLargeImage  
 Précise si le bouton affiche une image grande ou petite quand l‘utilisateur réduit le bouton.  
  
```  
void SetAlwaysLargeImage(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 Si `TRUE`, le bouton affiche une grande image. Dans le cas contraire, le bouton affiche une petite image.  
  
##  <a name="a-namesetdefaultcommanda--cmfcribbonbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFCRibbonButton::SetDefaultCommand  
 Active la commande par défaut pour le bouton du ruban.  
  
```  
void SetDefaultCommand(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 Si `TRUE`, le bouton peut exécuter une commande par défaut. Si `FALSE`, le bouton ne peut pas exécuter la commande par défaut.  
  
### <a name="remarks"></a>Notes  
 `bSet`s’applique uniquement lorsque le bouton possède un menu. Si `bSet` est `TRUE`, le bouton peut exécuter une commande par défaut et le menu contextuel assigné s’affiche uniquement lorsqu’un utilisateur clique sur la flèche à droite du bouton. Sinon, le bouton ne peut pas exécuter la commande par défaut et le menu contextuel s’affiche quelle que soit la zone du bouton que l’utilisateur clique.  
  
##  <a name="a-namesetdescriptiona--cmfcribbonbuttonsetdescription"></a><a name="setdescription"></a>CMFCRibbonButton::SetDescription  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszText`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetimageindexa--cmfcribbonbuttonsetimageindex"></a><a name="setimageindex"></a>CMFCRibbonButton::SetImageIndex  
 Affecte un index à l'image du bouton.  
  
```  
void SetImageIndex(
    int nIndex,  
    BOOL bLargeImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index d’image.  
  
 [in] `bLargeImage`  
 Si `TRUE`, l’index spécifié fait référence à la liste des images de grande taille. Dans le cas contraire, l’index fait référence à la liste des petites images.  
  
##  <a name="a-namesetmenua--cmfcribbonbuttonsetmenu"></a><a name="setmenu"></a>CMFCRibbonButton::SetMenu  
 Affecte un menu contextuel au bouton du ruban.  
  
```  
void SetMenu(
    HMENU hMenu,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);

void SetMenu(
    UINT uiMenuResID,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `hMenu`  
 Handle d’un menu Windows.  
  
 `bIsDefaultCommand`  
 Si `TRUE`, le bouton peut exécuter une commande par défaut ; sinon, le bouton affiche un menu contextuel.  
  
 `bRightAlign`  
 Si `TRUE`, le menu est aligné à droite. Sinon, le menu est aligné à gauche.  
  
 `uiMenuResID`  
 Un ID de ressource de menu.  
  
### <a name="remarks"></a>Remarques  
 Lorsque l’application affecte le menu du bouton, le bouton affiche une flèche sur le côté droit. Si `bIsDefaultCommand` est `TRUE`, le menu s’affiche uniquement lorsque l’utilisateur clique sur la flèche. Si l’utilisateur clique sur le bouton, la commande par défaut est exécutée. Si `bIsDefaultCommand` est `FALSE`, le menu s’affiche en cliquant sur le bouton.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbuttonsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButton::SetParentCategory  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParent`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetrightalignmenua--cmfcribbonbuttonsetrightalignmenu"></a><a name="setrightalignmenu"></a>CMFCRibbonButton::SetRightAlignMenu  
 Aligne le menu contextuel sur le bord du bouton.  
  
```  
void SetRightAlignMenu(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 Si `TRUE`, le menu est aligné à droite. Sinon, le menu est aligné à gauche  
  
##  <a name="a-namesettexta--cmfcribbonbuttonsettext"></a><a name="settext"></a>CMFCRibbonButton::SetText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszText`  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

