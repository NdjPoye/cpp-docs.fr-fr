---
title: Classe de CMFCRibbonBaseElement | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonBaseElement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonBaseElement class
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
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
ms.openlocfilehash: c596d7ef6ba87ca0f084c03856cf4f54dc8eac49
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbaseelement-class"></a>CMFCRibbonBaseElement (classe)
Le `CMFCRibbonBaseElement` est la classe de base pour tous les éléments que vous pouvez ajouter à un [barre ruban](../../mfc/reference/cmfcribbonbar-class.md). Parmi les exemples d'éléments de ruban figurent les boutons de ruban, les cases à cocher de ruban et les zones de listes déroulantes de ruban.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonBaseElement`|Construit un objet `CMFCRibbonBaseElement`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonBaseElement::AddToKeyList](#addtokeylist)|Ajoute une touche d’accès de l’élément de ruban à un tableau des touches accélératrices.|  
|[CMFCRibbonBaseElement::AddToListBox](#addtolistbox)|Ajoute un élément de ruban à la zone de liste des commandes de ruban spécifié.|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](#canbeaddedtoquickaccesstoolbar)|Indique si l’élément de ruban peut être ajouté à la barre d’outils Accès rapide.|  
|[CMFCRibbonBaseElement::CanBeCompacted](#canbecompacted)|Indique si la taille de l’élément de ruban peut être compacte.|  
|[CMFCRibbonBaseElement::CanBeStretched](#canbestretched)|Indique si la hauteur de l’élément de ruban peut augmenter verticalement à la hauteur d’une ligne de ruban.|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](#canbestretchedhorizontally)|Indique si la largeur de l’élément de ruban peut changer.|  
|[CMFCRibbonBaseElement::CleanUpSizes](#cleanupsizes)|Nettoie les paramètres de dimension pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::ClosePopupMenu](#closepopupmenu)|Ferme le menu contextuel pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::CopyFrom](#copyfrom)|Copie de l’état de l’objet `CMFCRibbonBaseElement` à l’objet actuel.|  
|[CMFCRibbonBaseElement::DestroyCtrl](#destroyctrl)|Supprime l’élément de ruban.|  
|[CMFCRibbonBaseElement::DrawImage](#drawimage)|Dessine l’image pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::Find](#find)|Retourne le pointeur spécifié vers l’élément ribbon s’il pointe vers l’objet actuel.|  
|[CMFCRibbonBaseElement::FindByData](#findbydata)|Récupère un pointeur vers l’élément ribbon s’il contient les données spécifiées.|  
|[CMFCRibbonBaseElement::FindByID](#findbyid)|Récupère un pointeur vers l’élément ribbon si cet élément est identifié par l’ID de commande spécifié.|  
|[CMFCRibbonBaseElement::FindByOriginal](#findbyoriginal)|Récupère un pointeur vers l’élément ribbon si son élément de ruban d’origine correspond à l’élément de ruban spécifié.|  
|[CMFCRibbonBaseElement::GetCompactSize](#getcompactsize)|Retourne la taille réduite de l'élément de ruban.|  
|[CMFCRibbonBaseElement::GetData](#getdata)|Récupère les données définies par l’utilisateur associées à l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetDescription](#getdescription)|Retourne la description de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetDroppedDown](#getdroppeddown)|Récupère un pointeur vers l’élément ribbon s’est déroulée son menu contextuel.|  
|[CMFCRibbonBaseElement::GetElements](#getelements)|Ajoute l’élément de ruban actuelle dans le tableau spécifié.|  
|[CMFCRibbonBaseElement::GetElementsByID](#getelementsbyid)|Ajoute l’élément de ruban actuelle dans le tableau spécifié si l’élément de ruban actuelle contient l’ID de commande spécifié.|  
|[CMFCRibbonBaseElement::GetHighlighted](#gethighlighted)|Récupère un pointeur vers l’élément ribbon si elle est mise en surbrillance.|  
|[CMFCRibbonBaseElement::GetID](#getid)|Retourne l’ID de commande de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetImageSize](#getimagesize)|Retourne la taille d'image de l'élément de ruban.|  
|[CMFCRibbonBaseElement::GetIntermediateSize](#getintermediatesize)|Retourne la taille de l'élément de ruban dans son état intermédiaire.|  
|[CMFCRibbonBaseElement::GetKeys](#getkeys)|Retourne la touche d’accès associée à l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetKeyTipRect](#getkeytiprect)|Récupère le rectangle de limite de touche d’accès de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetKeyTipSize](#getkeytipsize)|Récupère la taille du texte de la touche d’accès.|  
|[CMFCRibbonBaseElement::GetLocationInGroup](#getlocationingroup)|Indique l’emplacement d’affichage de l’élément de ruban dans un groupe de ruban.|  
|[CMFCRibbonBaseElement::GetMenuKeys](#getmenukeys)|Renvoie l’info-bulle associé à un bouton.|  
|[CMFCRibbonBaseElement::GetNotifyID](#getnotifyid)|Récupère l’ID de commande de notification pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetOriginal](#getoriginal)|Récupère l’élément de ruban d’origine.|  
|[CMFCRibbonBaseElement::GetParentCategory](#getparentcategory)|Récupère la catégorie de ruban de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetParentPanel](#getparentpanel)|Récupère le volet du ruban qui contient l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](#getparentribbonbar)|Récupère le ruban du parent de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetParentWnd](#getparentwnd)|Récupère la fenêtre parente de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetPressed](#getpressed)|Récupère un pointeur vers l’élément ribbon si actuellement, l’utilisateur appuie dessus.|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](#getquickaccesstoolbarid)|Récupère l’ID de commande de l’élément de ruban lorsqu’il est situé dans la barre d’outils Accès rapide.|  
|[CMFCRibbonBaseElement::GetRect](#getrect)|Retourne le rectangle englobant de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetRegularSize](#getregularsize)|Retourne la taille normale de l'élément de ruban.|  
|[CMFCRibbonBaseElement::GetSize](#getsize)|Retourne la taille actuelle de l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetText](#gettext)|Renvoie le texte associé à l’élément de ruban.|  
|[CMFCRibbonBaseElement::GetToolTipText](#gettooltiptext)|Retourne le texte d'info-bulle de l'élément de ruban.|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](#gettoplevelribbonbar)|Récupère la barre Ruban de niveau supérieur de l’élément de ruban.|  
|[CMFCRibbonBaseElement::HasCompactMode](#hascompactmode)|Précise si l'élément de ruban a un mode réduit.|  
|[CMFCRibbonBaseElement::HasFocus](#hasfocus)|Indique si l’élément parent a le focus clavier.|  
|[CMFCRibbonBaseElement::HasIntermediateMode](#hasintermediatemode)|Précise si l'élément de ruban a un mode intermédiaire.|  
|[CMFCRibbonBaseElement::HasLargeMode](#haslargemode)|Spécifie si l’élément de ruban dispose d’un mode de grande taille.|  
|[CMFCRibbonBaseElement::HasMenu](#hasmenu)|Indique si l’élément de ruban possède un menu.|  
|[CMFCRibbonBaseElement::HitTest](#hittest)|Récupère un pointeur vers l’élément ribbon si le point spécifié se trouve dans celui-ci.|  
|[CMFCRibbonBaseElement::IsAlignByColumn](#isalignbycolumn)|Indique si l’élément de ruban est alignée verticalement avec d’autres éléments de ruban.|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](#isalwayslargeimage)|Indique si la taille d’image de l’élément du ruban est toujours important.|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](#isautorepeatmode)|Indique si l’élément de ruban est automatiquement en mode de répétition.|  
|[CMFCRibbonBaseElement::IsChecked](#ischecked)|Spécifie si l’élément de ruban est vérifiée.|  
|[CMFCRibbonBaseElement::IsCompactMode](#iscompactmode)|Spécifie si l’élément de ruban est en mode compact.|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](#isdefaultmenulook)||  
|[CMFCRibbonBaseElement::IsDisabled](#isdisabled)|Spécifie si l’élément de ruban est désactivé.|  
|[CMFCRibbonBaseElement::IsDroppedDown](#isdroppeddown)|Détermine si l’élément de ruban affiche un menu contextuel et est déroulée.|  
|[CMFCRibbonBaseElement::IsFocused](#isfocused)|Spécifie si l’élément de ruban a le focus.|  
|[CMFCRibbonBaseElement::IsGalleryIcon](#isgalleryicon)|Indique si l’élément de ruban est contenue dans une galerie de ruban.|  
|[CMFCRibbonBaseElement::IsHighlighted](#ishighlighted)|Spécifie si l’élément de ruban est mis en surbrillance.|  
|[CMFCRibbonBaseElement::IsIntermediateMode](#isintermediatemode)|Indique si l’image actuelle pour l’élément de ruban est de taille intermédiaire.|  
|[CMFCRibbonBaseElement::IsLargeMode](#islargemode)|Indique si l’image actuelle de l’élément de ruban est grande taille.|  
|[CMFCRibbonBaseElement::IsMenuMode](#ismenumode)|Indique si l’élément de ruban est contenue dans un menu.|  
|[CMFCRibbonBaseElement::IsPressed](#ispressed)|Indique si l’utilisateur a cliqué sur l’élément de ruban.|  
|[CMFCRibbonBaseElement::IsQATMode](#isqatmode)|Indique si l’élément de ruban est contenue dans la barre d’outils Accès rapide.|  
|[CMFCRibbonBaseElement::IsSeparator](#isseparator)|Indique si l’élément de ruban est un séparateur d’affichage.|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](#isshowgroupborder)|Indique si l’élément de ruban est contenue dans un groupe qui affiche une frontière commune.|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](#isshowtooltiponbottom)|Indique si l’info-bulle est affichée sous l’élément de ruban.|  
|[CMFCRibbonBaseElement::IsTabStop](#istabstop)|Indique si l’élément de ruban peut être sélectionné à l’aide du clavier.|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](#istextalwaysonright)|Indique si le texte de l’élément de ruban est affiché sur la droite.|  
|[CMFCRibbonBaseElement::IsVisible](#isvisible)|Indique si l’élément de ruban est actuellement affiché.|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](#iswholerowheight)|Indique si la hauteur d’affichage de l’élément de ruban est identique à la hauteur d’affichage du Panneau de ruban qui le contient.|  
|[CMFCRibbonBaseElement::NotifyCommand](#notifycommand)|Envoie une notification de commande de la fenêtre parente de l’élément de ruban.|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](#notifyhighlightlistitem)|Avertit la fenêtre parente de la barre Ruban lorsqu’un utilisateur met en surbrillance un élément de ruban qui se trouve dans une liste.|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](#onaddtoqatoolbar)|Ajoute l’élément de ruban à la barre d’outils Accès rapide spécifié.|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](#onafterchangerect)|Met à jour l’info-bulle pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::OnAutoRepeat](#onautorepeat)|Met à jour l’élément de ruban en réponse à une entrée utilisateur soutenue.|  
|[CMFCRibbonBaseElement::OnCalcTextSize](#oncalctextsize)|Calcule la taille du texte de l’élément de ruban.|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](#onchangemenuhighlight)|Appelé par l’infrastructure lorsque la sélection change pour un élément de ruban qui se trouve dans un menu.|  
|[CMFCRibbonBaseElement::OnDraw](#ondraw)|Appelé par l'infrastructure pour dessiner l'élément de ruban.|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](#ondrawkeytip)|Appelé par l’infrastructure pour dessiner la touche d’accès de l’élément de ruban.|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](#ondrawmenuimage)|Appelé par l’infrastructure lors du dessin de l’image de menu pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::OnDrawOnList](#ondrawonlist)|Appelé par l’infrastructure pour dessiner l’élément de ruban dans une zone de liste de commandes.|  
|[CMFCRibbonBaseElement::OnKey](#onkey)|Appelé par l’infrastructure lorsque l’utilisateur appuie sur une touche d’accès et l’élément de ruban a le focus.|  
|[CMFCRibbonBaseElement::OnMenuKey](#onmenukey)||  
|[CMFCRibbonBaseElement::OnRTLChanged](#onrtlchanged)|Appelé par l’infrastructure lorsque la disposition change de direction.|  
|[CMFCRibbonBaseElement::OnShow](#onshow)|Appelé par l’infrastructure pour afficher ou masquer l’élément de ruban.|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](#onshowpopupmenu)|Appelé par l’infrastructure lorsque l’élément de ruban va afficher un menu contextuel.|  
|[CMFCRibbonBaseElement::PostMenuCommand](#postmenucommand)||  
|[CMFCRibbonBaseElement::Redraw](#redraw)|Met à jour l’affichage de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetACCData](#setaccdata)|Définit les données d’accessibilité de l’élément ruban.|  
|[CMFCRibbonBaseElement::SetCompactMode](#setcompactmode)|Définit la taille d’affichage de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetData](#setdata)|Associe un élément de données à l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](#setdefaultmenulook)||  
|[CMFCRibbonBaseElement::SetDescription](#setdescription)|Définit la description de l'élément de ruban.|  
|[CMFCRibbonBaseElement::SetID](#setid)|Définit l’ID de commande de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetInitialMode](#setinitialmode)|Définit la taille d’affichage initial de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetKeys](#setkeys)|Définit une touche d’accès de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetOriginal](#setoriginal)|Définit l’élément de ruban d’origine pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetParentCategory](#setparentcategory)|Définit la catégorie parente de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetParentMenu](#setparentmenu)|Définit le parent conteneur du menu de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](#setparentribbonbar)|Définit la barre de ruban parent pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetRect](#setrect)|Définit le synthétique de dimensions pour qu’il affiche le rectangle de l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetText](#settext)|Définit le texte de l'élément de ruban.|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](#settextalwaysonright)|Définit le texte de l’élément de ruban à afficher sur la droite.|  
|[CMFCRibbonBaseElement::SetToolTipText](#settooltiptext)|Définit le texte info-bulle pour l’élément de ruban.|  
|[CMFCRibbonBaseElement::SetVisible](#setvisible)|Définit l’état de visibilité de l’élément de ruban.|  
|[CMFCRibbonBaseElement::StretchHorizontally](#stretchhorizontally)|Étend la largeur de l’élément de ruban.|  
|[CMFCRibbonBaseElement::StretchToWholeRow](#stretchtowholerow)|Modifie la hauteur d’affichage de l’élément de ruban de la hauteur de ligne spécifiée.|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](#updatetooltipinfo)|Met à jour le texte d’info-bulle à l’aide de la ressource de commande pour l’élément de ruban.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonBaseElement::OnProcessKey](#onprocesskey)|Appelé par l’infrastructure lorsque l’utilisateur appuie sur une touche de raccourci.|  
|[CMFCRibbonBaseElement::OnSetFocus](#onsetfocus)|Appelé par l’infrastructure lorsqu’un élément de ruban reçoit ou perd le focus d’entrée.|  
  
## <a name="remarks"></a>Remarques  
 La `CMFCRibbonBaseElement` classe définit les propriétés qui sont communes à tous les éléments de ruban qui incluent l’ID de commande, étiquette de texte, texte info-bulle, description de l’élément et l’état (qui peut être actif, mis en surbrillance, enfoncé, désactivé, activé ou déroulée).  
  
 La taille de l’image d’un élément de ruban est définie par le `RibbonImageType` membre, qui peut être une des valeurs suivantes :  
  
- `RibbonImageLarge`  
  
- `RibbonImageSmall`  
  
 En fonction de sa taille, un élément de ruban affiche une image de petite ou grande.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCRibbonBaseElement` classe. L’exemple montre comment obtenir un `CMFCRibbonBaseElement` de l’objet d’un `CMFCRibbonStatusBar` classe, définissez la description de l’élément de ruban, définir le texte, définir une touche d’accès et le texte d’info-bulle pour l’élément de ruban. Cet extrait de code fait partie de la [Client dessiner, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient n °&8;](../../mfc/reference/codesnippet/cpp/cmfcribbonbaseelement-class_1.cpp)]  
[!code-cpp[NVC_MFC_DrawClient&#9;](../../mfc/reference/codesnippet/cpp/cmfcribbonbaseelement-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxbaseribbonelement.h  
  
##  <a name="a-nameaddtokeylista--cmfcribbonbaseelementaddtokeylist"></a><a name="addtokeylist"></a>CMFCRibbonBaseElement::AddToKeyList  
 Ajoute une touche d’accès de l’élément de ruban à un tableau des touches accélératrices.  
  
```  
virtual void AddToKeyList(
    CArray<CMFCRibbonKeyTip*, CMFCRibbonKeyTip*>& arElems);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `arElems`  
 Référence à un [CArray](../../mfc/reference/carray-class.md) de combinaisons de touches.  
  
### <a name="remarks"></a>Notes  
 Lorsque la fonctionnalité de combinaisons de touches du ruban est activée, le framework affiche les combinaisons de touches du ruban lorsque l’utilisateur appuie sur la touche ALT ou F10.  
  
##  <a name="a-nameaddtolistboxa--cmfcribbonbaseelementaddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonBaseElement::AddToListBox  
 Ajoute un élément de ruban à la zone de liste des commandes de ruban spécifié.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndListBox`  
 Pointeur vers une zone de liste de commandes.  
  
 [in] `bDeep`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément de ruban ajouté.  
  
### <a name="remarks"></a>Remarques  
 Le framework ajoute les éléments de ruban à une zone de liste de commandes pour permettre aux utilisateurs de personnaliser l’interface utilisateur.  
  
##  <a name="a-namecanbeaddedtoquickaccesstoolbara--cmfcribbonbaseelementcanbeaddedtoquickaccesstoolbar"></a><a name="canbeaddedtoquickaccesstoolbar"></a>CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar  
 Indique si l’élément de ruban peut être ajouté à la barre d’outils Accès rapide.  
  
```  
virtual BOOL CanBeAddedToQuickAccessToolBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément peut être ajouté ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecanbecompacteda--cmfcribbonbaseelementcanbecompacted"></a><a name="canbecompacted"></a>CMFCRibbonBaseElement::CanBeCompacted  
 Indique si la taille de l’élément de ruban peut être compacte.  
  
```  
virtual BOOL CanBeCompacted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la taille de l’élément de ruban peut être compacte ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 La taille d’un élément de ruban peut être compact, intermédiaire ou de grande taille.  
  
##  <a name="a-namecanbestretcheda--cmfcribbonbaseelementcanbestretched"></a><a name="canbestretched"></a>CMFCRibbonBaseElement::CanBeStretched  
 Indique si la hauteur de l’élément de ruban peut augmenter verticalement à la hauteur d’une ligne de ruban.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode retourne toujours `TRUE`. Substituez cette méthode pour indiquer si la hauteur de l’élément de ruban peut augmenter verticalement à la hauteur d’une ligne de ruban.  
  
##  <a name="a-namecanbestretchedhorizontallya--cmfcribbonbaseelementcanbestretchedhorizontally"></a><a name="canbestretchedhorizontally"></a>CMFCRibbonBaseElement::CanBeStretchedHorizontally  
 Indique si la largeur de l’élément de ruban peut changer.  
  
```  
virtual BOOL CanBeStretchedHorizontally();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode pour indiquer si la largeur de l’élément de ruban peut modifier.  
  
##  <a name="a-namecleanupsizesa--cmfcribbonbaseelementcleanupsizes"></a><a name="cleanupsizes"></a>CMFCRibbonBaseElement::CleanUpSizes  
 Nettoie les paramètres de dimension pour l’élément de ruban.  
  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode dans une classe dérivée pour réinitialiser les paramètres de dimension de l’élément de ruban.  
  
##  <a name="a-nameclosepopupmenua--cmfcribbonbaseelementclosepopupmenu"></a><a name="closepopupmenu"></a>CMFCRibbonBaseElement::ClosePopupMenu  
 Ferme le menu contextuel pour l’élément de ruban.  
  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecopyfroma--cmfcribbonbaseelementcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonBaseElement::CopyFrom  
 Copie de l’état de l’objet [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) à l’objet actuel.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `src`  
 La source de [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedestroyctrla--cmfcribbonbaseelementdestroyctrl"></a><a name="destroyctrl"></a>CMFCRibbonBaseElement::DestroyCtrl  
 Supprime l’élément de ruban.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode dans une classe dérivée pour détruire l’élément de ruban.  
  
##  <a name="a-namedrawimagea--cmfcribbonbaseelementdrawimage"></a><a name="drawimage"></a>CMFCRibbonBaseElement::DrawImage  
 Dessine l’image pour l’élément de ruban.  
  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `type`  
 Un type d’image de valeur énumérée. Consultez la section Notes pour obtenir la liste des valeurs possibles.  
  
 [in] `rectImage`  
 Le rectangle de l’image.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode dans une classe dérivée pour dessiner l’image pour l’élément de ruban.  
  
 Le tableau suivant répertorie les valeurs possibles pour le `type` paramètre :  
  
 `RibbonImageLarge`  
 Grande taille d’image de 32 x 32 pixels.  
  
 `RibbonImageSmall`  
 Petite taille de l’image 16 x 16 pixels.  
  
##  <a name="a-namefinda--cmfcribbonbaseelementfind"></a><a name="find"></a>CMFCRibbonBaseElement::Find  
 Retourne le pointeur spécifié s’il pointe vers l’objet actuel.  
  
```  
virtual CMFCRibbonBaseElement* Find(const CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElement`  
 Pointeur vers un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément ribbon si `pElement` pointe vers l’objet actuel ; sinon `NULL`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namefindbydataa--cmfcribbonbaseelementfindbydata"></a><a name="findbydata"></a>CMFCRibbonBaseElement::FindByData  
 Récupère un pointeur vers l’élément ribbon s’il contient les données spécifiées.  
  
```  
virtual CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwData`  
 Les données associées à un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément ribbon s’il contient les données spécifiées ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namefindbyida--cmfcribbonbaseelementfindbyid"></a><a name="findbyid"></a>CMFCRibbonBaseElement::FindByID  
 Récupère un pointeur vers l’élément ribbon si cet élément est identifié par l’ID de commande spécifié.  
  
```  
virtual CMFCRibbonBaseElement* FindByID(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 ID de commande pour un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de ruban si cet élément est identifié par l’ID de la commande spécifiée ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namefindbyoriginala--cmfcribbonbaseelementfindbyoriginal"></a><a name="findbyoriginal"></a>CMFCRibbonBaseElement::FindByOriginal  
 Récupère un pointeur vers l’élément de ruban actuelle si son élément de ruban d’origine correspond à l’élément de ruban spécifié.  
  
```  
virtual CMFCRibbonBaseElement* FindByOriginal(CMFCRibbonBaseElement* pOriginal);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pOriginal`  
 Pointeur vers un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de ruban si son élément de ruban d’origine correspond à l’élément spécifié de ruban ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
 Les éléments de ruban qui sont copiés vers un autre conteneur conservent un pointeur vers l’élément de ruban d’origine.  
  
##  <a name="a-namegetcompactsizea--cmfcribbonbaseelementgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonBaseElement::GetCompactSize  
 Retourne la taille réduite de l'élément de ruban.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 Compacte d’un élément de ruban.  
  
> [!NOTE]
>  Compacte signifie que l’élément de ruban est tronqué (il affiche une petite image ou une image sans texte).  
  
##  <a name="a-namegetdataa--cmfcribbonbaseelementgetdata"></a><a name="getdata"></a>CMFCRibbonBaseElement::GetData  
 Récupère les données définies par l’utilisateur associées à l’élément de ruban.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les données définies par l’utilisateur associées à l’élément de ruban.  
  
##  <a name="a-namegetdescriptiona--cmfcribbonbaseelementgetdescription"></a><a name="getdescription"></a>CMFCRibbonBaseElement::GetDescription  
 Retourne la description de l’élément de ruban.  
  
```  
virtual CString GetDescription() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La description de l’élément du ruban. La description est affichée sur la barre d’état, ou dans une info-bulle ou sous le bouton de menu si l’élément de ruban se trouve sur le [CMFCRibbonMainPanel classe](../../mfc/reference/cmfcribbonmainpanel-class.md).  
  
##  <a name="a-namegetdroppeddowna--cmfcribbonbaseelementgetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonBaseElement::GetDroppedDown  
 Récupère un pointeur vers l’élément ribbon s’est déroulée son menu contextuel.  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de ruban si son menu contextuel est supprimée dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetelementsa--cmfcribbonbaseelementgetelements"></a><a name="getelements"></a>CMFCRibbonBaseElement::GetElements  
 Ajoute l’élément de ruban actuelle dans le tableau spécifié.  
  
```  
virtual void GetElements(
    CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `arElements`  
 Tableau d’éléments de ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetelementsbyida--cmfcribbonbaseelementgetelementsbyid"></a><a name="getelementsbyid"></a>CMFCRibbonBaseElement::GetElementsByID  
 Ajoute l’élément de ruban actuelle dans le tableau spécifié si l’élément de ruban actuelle contient l’ID de commande spécifié.  
  
```  
virtual void GetElementsByID(
    UINT uiCmdID,  
    CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 ID de commande d’un élément de ruban.  
  
 [in] `arElements`  
 Tableau d’éléments de ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegethighlighteda--cmfcribbonbaseelementgethighlighted"></a><a name="gethighlighted"></a>CMFCRibbonBaseElement::GetHighlighted  
 Récupère un pointeur vers l’élément ribbon si elle est mise en surbrillance.  
  
```  
virtual CMFCRibbonBaseElement* GetHighlighted();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de ruban si elle est mise en surbrillance ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetida--cmfcribbonbaseelementgetid"></a><a name="getid"></a>CMFCRibbonBaseElement::GetID  
 Retourne l’ID de commande de l’élément de ruban.  
  
```  
UINT GetID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de l’élément de ruban.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbaseelementgetimagesize"></a><a name="getimagesize"></a>CMFCRibbonBaseElement::GetImageSize  
 Retourne la taille d'image de l'élément de ruban.  
  
```  
virtual CSize GetImageSize(RibbonImageType R) const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de l’image de l’élément de ruban.  
  
##  <a name="a-namegetintermediatesizea--cmfcribbonbaseelementgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonBaseElement::GetIntermediateSize  
 Retourne la taille de l'élément de ruban dans son état intermédiaire.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de l’élément de ruban dans son état intermédiaire.  
  
##  <a name="a-namegetkeysa--cmfcribbonbaseelementgetkeys"></a><a name="getkeys"></a>CMFCRibbonBaseElement::GetKeys  
 Retourne la touche d’accès associée à l’élément de ruban.  
  
```  
LPCTSTR GetKeys() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une touche d’accès associée à l’élément de ruban.  
  
##  <a name="a-namegetkeytiprecta--cmfcribbonbaseelementgetkeytiprect"></a><a name="getkeytiprect"></a>CMFCRibbonBaseElement::GetKeyTipRect  
 Récupère le rectangle de limite de touche d’accès de l’élément de ruban.  
  
```  
virtual CRect GetKeyTipRect(
    CDC* pDC,  
    BOOL bIsMenu);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `bIsMenu`  
 `TRUE`Si l’élément de ruban affiche un menu contextuel. dans le cas contraire `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours un rectangle avec les valeurs 0.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode dans une classe dérivée pour retourner le rectangle de limite de touche d’accès.  
  
##  <a name="a-namegetkeytipsizea--cmfcribbonbaseelementgetkeytipsize"></a><a name="getkeytipsize"></a>CMFCRibbonBaseElement::GetKeyTipSize  
 Récupère la taille du texte de la touche d’accès.  
  
```  
virtual CSize GetKeyTipSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille du texte de touche d’accès.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetlocationingroupa--cmfcribbonbaseelementgetlocationingroup"></a><a name="getlocationingroup"></a>CMFCRibbonBaseElement::GetLocationInGroup  
 Indique l’emplacement d’affichage de l’élément de ruban dans un groupe de ruban.  
  
```  
RibbonElementLocation GetLocationInGroup() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `RibbonElementLocation` valeur énumérée. Le tableau suivant répertorie les valeurs possibles.  
  
|Valeur|Description|  
|-----------|-----------------|  
|`RibbonElementNotInGroup`|L’élément de ruban n’est pas contenu dans un groupe de ruban.|  
|`RibbonElementSingleInGroup`|L’élément de ruban est affiché en tant que le seul élément dans un groupe de ruban.|  
|`RibbonElementFirstInGroup`|L’élément de ruban est affiché à l’extrémité gauche d’un groupe de ruban.|  
|`RibbonElementLastInGroup`|L’élément de ruban est affiché à l’extrémité droite d’un groupe de ruban.|  
|`RibbonElementMiddleInGroup`|L’élément de ruban ne s’affiche pas sur des extrémités d’un groupe de ruban.|  
  
### <a name="remarks"></a>Remarques  
 Groupes d’éléments du ruban sont alignées uniquement horizontalement.  
  
##  <a name="a-namegetmenukeysa--cmfcribbonbaseelementgetmenukeys"></a><a name="getmenukeys"></a>CMFCRibbonBaseElement::GetMenuKeys  
 Retourne la touche d’accès menu pour l’élément de ruban.  
  
```  
LPCTSTR GetMenuKeys() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La touche d’accès menu associé à l’élément de ruban.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’elle est appelée, une touche d’accès menu affiche un menu contextuel.  
  
##  <a name="a-namegetnotifyida--cmfcribbonbaseelementgetnotifyid"></a><a name="getnotifyid"></a>CMFCRibbonBaseElement::GetNotifyID  
 Récupère l’ID de commande de notification pour l’élément de ruban.  
  
```  
virtual UINT GetNotifyID();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de notification.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetoriginala--cmfcribbonbaseelementgetoriginal"></a><a name="getoriginal"></a>CMFCRibbonBaseElement::GetOriginal  
 Récupère l’élément de ruban d’origine.  
  
```  
CMFCRibbonBaseElement* GetOriginal() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément de ruban d’origine.  
  
### <a name="remarks"></a>Remarques  
 Les éléments de ruban qui sont copiés vers un autre conteneur conservent un pointeur vers l’élément de ruban d’origine.  
  
##  <a name="a-namegetparentcategorya--cmfcribbonbaseelementgetparentcategory"></a><a name="getparentcategory"></a>CMFCRibbonBaseElement::GetParentCategory  
 Récupère la catégorie de ruban de l’élément de ruban.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la catégorie de ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetparentpanela--cmfcribbonbaseelementgetparentpanel"></a><a name="getparentpanel"></a>CMFCRibbonBaseElement::GetParentPanel  
 Récupère le volet du ruban qui contient l’élément de ruban.  
  
```  
virtual CMFCRibbonPanel* GetParentPanel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le volet du ruban qui contient l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetparentribbonbara--cmfcribbonbaseelementgetparentribbonbar"></a><a name="getparentribbonbar"></a>CMFCRibbonBaseElement::GetParentRibbonBar  
 Récupère le ruban du parent de l’élément de ruban.  
  
```  
CMFCRibbonBar* GetParentRibbonBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la barre de ruban parent pour l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetparentwnda--cmfcribbonbaseelementgetparentwnd"></a><a name="getparentwnd"></a>CMFCRibbonBaseElement::GetParentWnd  
 Récupère la fenêtre parente de l’élément de ruban.  
  
```  
virtual CWnd* GetParentWnd() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la fenêtre parente de l’élément de ruban si la méthode a réussi ; dans le cas contraire, `NULL`.  
  
### <a name="remarks"></a>Notes  
 La fenêtre parent pour un élément de ruban est une [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) ou [CMFCRibbonPanelMenuBar](http://msdn.microsoft.com/en-us/7bd4b986-8b7b-493e-9746-bd3161b78581).  
  
##  <a name="a-namegetpresseda--cmfcribbonbaseelementgetpressed"></a><a name="getpressed"></a>CMFCRibbonBaseElement::GetPressed  
 Récupère un pointeur vers l’élément ribbon si actuellement, l’utilisateur appuie dessus.  
  
```  
virtual CMFCRibbonBaseElement* GetPressed();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de ruban si l’utilisateur appuie sur actuellement dans le cas contraire, `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetquickaccesstoolbarida--cmfcribbonbaseelementgetquickaccesstoolbarid"></a><a name="getquickaccesstoolbarid"></a>CMFCRibbonBaseElement::GetQuickAccessToolBarID  
 Récupère l’ID de commande de l’élément de ruban lorsqu’il est situé dans la barre d’outils Accès rapide.  
  
```  
virtual UINT GetQuickAccessToolBarID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de l’élément de ruban lorsqu’il est situé dans la barre d’outils Accès rapide.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetrecta--cmfcribbonbaseelementgetrect"></a><a name="getrect"></a>CMFCRibbonBaseElement::GetRect  
 Retourne le rectangle englobant de l’élément de ruban.  
  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rectangle englobant de l’élément de ruban. La position du rectangle est dans les coordonnées du ruban contrôle parent.  
  
##  <a name="a-namegetregularsizea--cmfcribbonbaseelementgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonBaseElement::GetRegularSize  
 Retourne la taille normale de l'élément de ruban.  
  
```  
virtual CSize GetRegularSize(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille standard de l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  La taille standard est la taille maximale possible de l’élément de ruban.  
  
##  <a name="a-namegetsizea--cmfcribbonbaseelementgetsize"></a><a name="getsize"></a>CMFCRibbonBaseElement::GetSize  
 Retourne la taille actuelle de l’élément de ruban.  
  
```  
virtual CSize GetSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 La taille actuelle de l’élément de ruban.  
  
##  <a name="a-namegettexta--cmfcribbonbaseelementgettext"></a><a name="gettext"></a>CMFCRibbonBaseElement::GetText  
 Renvoie le texte associé à l’élément de ruban.  
  
```  
LPCTSTR GetText() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le texte associé à l’élément de ruban.  
  
##  <a name="a-namegettooltiptexta--cmfcribbonbaseelementgettooltiptext"></a><a name="gettooltiptext"></a>CMFCRibbonBaseElement::GetToolTipText  
 Retourne le texte d'info-bulle de l'élément de ruban.  
  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le texte info-bulle de l’élément de ruban.  
  
##  <a name="a-namegettoplevelribbonbara--cmfcribbonbaseelementgettoplevelribbonbar"></a><a name="gettoplevelribbonbar"></a>CMFCRibbonBaseElement::GetTopLevelRibbonBar  
 Récupère la barre Ruban de niveau supérieur de l’élément de ruban.  
  
```  
CMFCRibbonBar* GetTopLevelRibbonBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la barre de ruban de niveau supérieur de l’élément de ruban si la méthode a réussi ; dans le cas contraire, `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehascompactmodea--cmfcribbonbaseelementhascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonBaseElement::HasCompactMode  
 Précise si l'élément de ruban a un mode réduit.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban dispose d’un mode compact. Sinon, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  En mode compact, un élément s’affiche uniquement une petite image.  
  
##  <a name="a-namehasintermediatemodea--cmfcribbonbaseelementhasintermediatemode"></a><a name="hasintermediatemode"></a>CMFCRibbonBaseElement::HasIntermediateMode  
 Précise si l'élément de ruban a un mode intermédiaire.  
  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban comporte un mode intermédiaire, `FALSE` dans le cas contraire. Dans le mode intermédiaire, un élément affiche une petite image et un texte à droite de l’image.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namehaslargemodea--cmfcribbonbaseelementhaslargemode"></a><a name="haslargemode"></a>CMFCRibbonBaseElement::HasLargeMode  
 Détermine si l'élément de ruban a un mode grand.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban dispose d’un mode de grande taille. Sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Dans le mode de grande taille, un élément peut prendre la hauteur totale du panneau parent.  
  
##  <a name="a-namehasmenua--cmfcribbonbaseelementhasmenu"></a><a name="hasmenu"></a>CMFCRibbonBaseElement::HasMenu  
 Indique si l’élément de ruban possède un menu.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode dans une classe dérivée pour indiquer si l’élément de ruban possède un menu.  
  
##  <a name="a-namehittesta--cmfcribbonbaseelementhittest"></a><a name="hittest"></a>CMFCRibbonBaseElement::HitTest  
 Récupère un pointeur vers l’élément ribbon si le point spécifié se trouve dans celui-ci.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément ribbon s’il existe ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode retourne toujours un pointeur valide à l’élément de ruban lorsqu’il existe. Substituez cette méthode pour indiquer si le point se trouve dans l’élément de ruban.  
  
##  <a name="a-nameisalignbycolumna--cmfcribbonbaseelementisalignbycolumn"></a><a name="isalignbycolumn"></a>CMFCRibbonBaseElement::IsAlignByColumn  
 Indique si l’élément de ruban est alignée verticalement avec d’autres éléments de ruban.  
  
```  
virtual BOOL IsAlignByColumn() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode retourne toujours `TRUE`. Substituez cette méthode dans une classe dérivée pour indiquer si l’élément de ruban dérivée est alignée verticalement avec d’autres éléments de ruban.  
  
##  <a name="a-nameisalwayslargeimagea--cmfcribbonbaseelementisalwayslargeimage"></a><a name="isalwayslargeimage"></a>CMFCRibbonBaseElement::IsAlwaysLargeImage  
 Indique si la taille d’image de l’élément du ruban est toujours important.  
  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la taille d’image de l’élément du ruban est toujours volumineux ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Taille de l’image de grande taille est de 32 x 32 pixels.  
  
##  <a name="a-nameisautorepeatmodea--cmfcribbonbaseelementisautorepeatmode"></a><a name="isautorepeatmode"></a>CMFCRibbonBaseElement::IsAutoRepeatMode  
 Indique si l’élément de ruban est automatiquement en mode de répétition.  
  
```  
virtual BOOL IsAutoRepeatMode(int& nDelay) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nDelay`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode pour indiquer si l’élément de ruban est automatiquement en mode de répétition.  
  
 Auto mode de répétition, l’élément de ruban répond à un intervalle défini, mesurée en millisecondes, à l’entrée utilisateur soutenue.  
  
##  <a name="a-nameischeckeda--cmfcribbonbaseelementischecked"></a><a name="ischecked"></a>CMFCRibbonBaseElement::IsChecked  
 Spécifie si l’élément de ruban est vérifiée.  
  
```  
virtual BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est activé ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameiscompactmodea--cmfcribbonbaseelementiscompactmode"></a><a name="iscompactmode"></a>CMFCRibbonBaseElement::IsCompactMode  
 Spécifie si l’élément de ruban est en mode compact.  
  
```  
BOOL IsCompactMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est en mode compact ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisdefaultmenulooka--cmfcribbonbaseelementisdefaultmenulook"></a><a name="isdefaultmenulook"></a>CMFCRibbonBaseElement::IsDefaultMenuLook  
 Indique si l’élément de ruban est définie sur apparaissent sous la forme d’une commande contextuelle.  
  
```  
BOOL IsDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la valeur de l’élément de ruban apparaisse comme une commande contextuelle ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisdisableda--cmfcribbonbaseelementisdisabled"></a><a name="isdisabled"></a>CMFCRibbonBaseElement::IsDisabled  
 Spécifie si l’élément de ruban est désactivé.  
  
```  
virtual BOOL IsDisabled() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est désactivé ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisdroppeddowna--cmfcribbonbaseelementisdroppeddown"></a><a name="isdroppeddown"></a>CMFCRibbonBaseElement::IsDroppedDown  
 Spécifie si l’élément de ruban affiche un menu contextuel et est déroulée.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est déroulée et affiche un menu contextuel. dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisfocuseda--cmfcribbonbaseelementisfocused"></a><a name="isfocused"></a>CMFCRibbonBaseElement::IsFocused  
 Spécifie si l’élément de ruban a le focus.  
  
```  
virtual BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban a le focus ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisgalleryicona--cmfcribbonbaseelementisgalleryicon"></a><a name="isgalleryicon"></a>CMFCRibbonBaseElement::IsGalleryIcon  
 Indique si l’élément de ruban est contenue dans une galerie de ruban.  
  
```  
virtual BOOL IsGalleryIcon() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode dans une classe dérivée pour indiquer si l’élément de ruban est contenue dans une galerie de ruban.  
  
##  <a name="a-nameishighlighteda--cmfcribbonbaseelementishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonBaseElement::IsHighlighted  
 Spécifie si l’élément de ruban est mis en surbrillance.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est mis en surbrillance ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisintermediatemodea--cmfcribbonbaseelementisintermediatemode"></a><a name="isintermediatemode"></a>CMFCRibbonBaseElement::IsIntermediateMode  
 Indique si l’image actuelle pour l’élément de ruban est de taille intermédiaire.  
  
```  
BOOL IsIntermediateMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image pour l’élément de ruban est de taille intermédiaire ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Taille de l’image intermédiaire est 16 x 16 pixels.  
  
##  <a name="a-nameislargemodea--cmfcribbonbaseelementislargemode"></a><a name="islargemode"></a>CMFCRibbonBaseElement::IsLargeMode  
 Indique si l’image actuelle pour l’élément de ruban est de grande taille.  
  
```  
BOOL IsLargeMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image pour l’élément de ruban est de grande taille ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Taille de l’image de grande taille est de 32 x 32 pixels.  
  
##  <a name="a-nameismenumodea--cmfcribbonbaseelementismenumode"></a><a name="ismenumode"></a>CMFCRibbonBaseElement::IsMenuMode  
 Indique si l’élément de ruban est contenue dans un menu.  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est contenu dans un menu. dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameispresseda--cmfcribbonbaseelementispressed"></a><a name="ispressed"></a>CMFCRibbonBaseElement::IsPressed  
 Indique si l’utilisateur a cliqué sur l’élément de ruban.  
  
```  
virtual BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’utilisateur a cliqué sur l’élément de ruban ; dans le cas contraire `FALSE`.  
  
##  <a name="a-nameisqatmodea--cmfcribbonbaseelementisqatmode"></a><a name="isqatmode"></a>CMFCRibbonBaseElement::IsQATMode  
 Indique si l’élément de ruban est contenue dans la barre d’outils Accès rapide.  
  
```  
BOOL IsQATMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est contenu dans la barre d’outils Accès rapide ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisseparatora--cmfcribbonbaseelementisseparator"></a><a name="isseparator"></a>CMFCRibbonBaseElement::IsSeparator  
 Indique si l’élément de ruban est un séparateur d’affichage.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est un séparateur d’affichage ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisshowgroupbordera--cmfcribbonbaseelementisshowgroupborder"></a><a name="isshowgroupborder"></a>CMFCRibbonBaseElement::IsShowGroupBorder  
 Indique si l’élément de ruban est contenue dans un groupe qui affiche une frontière commune.  
  
```  
BOOL IsShowGroupBorder() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est contenue dans un groupe qui affiche une bordure commune ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisshowtooltiponbottoma--cmfcribbonbaseelementisshowtooltiponbottom"></a><a name="isshowtooltiponbottom"></a>CMFCRibbonBaseElement::IsShowTooltipOnBottom  
 Indique si l’info-bulle est affichée sous l’élément de ruban.  
  
```  
virtual BOOL IsShowTooltipOnBottom() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’info-bulle est affichée sous l’élément de ruban ; `FALSE` si l’info-bulle est affiché près du pointeur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameistabstopa--cmfcribbonbaseelementistabstop"></a><a name="istabstop"></a>CMFCRibbonBaseElement::IsTabStop  
 Indique si l’élément de ruban peut être sélectionné à l’aide du clavier.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode retourne toujours `TRUE`. Substituez cette méthode pour indiquer si l’élément de ruban peut être sélectionné à l’aide du clavier.  
  
##  <a name="a-nameistextalwaysonrighta--cmfcribbonbaseelementistextalwaysonright"></a><a name="istextalwaysonright"></a>CMFCRibbonBaseElement::IsTextAlwaysOnRight  
 Indique si le texte de l’élément de ruban est affiché sur la droite.  
  
```  
BOOL IsTextAlwaysOnRight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le texte de l’élément de ruban est affiché à droite ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisvisiblea--cmfcribbonbaseelementisvisible"></a><a name="isvisible"></a>CMFCRibbonBaseElement::IsVisible  
 Indique si l’élément de ruban est actuellement affiché.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban est affichée ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameiswholerowheighta--cmfcribbonbaseelementiswholerowheight"></a><a name="iswholerowheight"></a>CMFCRibbonBaseElement::IsWholeRowHeight  
 Indique si la hauteur d’affichage de l’élément de ruban est identique à la hauteur d’affichage du Panneau de ruban qui le contient.  
  
```  
virtual BOOL IsWholeRowHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode pour indiquer si la hauteur d’affichage de l’élément de ruban est identique à la hauteur d’affichage du Panneau de ruban qui le contient.  
  
##  <a name="a-namenotifycommanda--cmfcribbonbaseelementnotifycommand"></a><a name="notifycommand"></a>CMFCRibbonBaseElement::NotifyCommand  
 Envoie une notification de commande de la fenêtre parente de l’élément de ruban.  
  
```  
BOOL NotifyCommand(BOOL bWithDelay = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bWithDelay`  
 `TRUE`Pour ajouter la notification de commande à la file d’attente de messages de la fenêtre parente. `FALSE` pour envoyer le message immédiatement à la fenêtre parente.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le message a été envoyé ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namenotifyhighlightlistitema--cmfcribbonbaseelementnotifyhighlightlistitem"></a><a name="notifyhighlightlistitem"></a>CMFCRibbonBaseElement::NotifyHighlightListItem  
 Avertit la fenêtre parente de la barre Ruban lorsqu’un utilisateur met en surbrillance un élément de ruban qui se trouve dans une liste.  
  
```  
virtual void NotifyHighlightListItem(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 L’index de l’élément de ruban dans la liste.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonaddtoqatoolbara--cmfcribbonbaseelementonaddtoqatoolbar"></a><a name="onaddtoqatoolbar"></a>CMFCRibbonBaseElement::OnAddToQAToolbar  
 Ajoute l’élément de ruban à la barre d’outils Accès rapide spécifié.  
  
```  
virtual BOOL OnAddToQAToolbar(CMFCRibbonQuickAccessToolBar& qat);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `qat`  
 La barre d’outils Accès rapide.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE` indiquant l’élément de ruban a été ajouté à la barre d’outils Accès rapide.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonafterchangerecta--cmfcribbonbaseelementonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonBaseElement::OnAfterChangeRect  
 Met à jour l’info-bulle pour l’élément de ruban.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Notes  
 Par défaut cette méthode met à jour l’info-bulle pour l’élément de ruban. Substituez cette méthode pour mettre à jour l’élément de ruban après que son rectangle d’affichage a été modifié.  
  
##  <a name="a-nameonautorepeata--cmfcribbonbaseelementonautorepeat"></a><a name="onautorepeat"></a>CMFCRibbonBaseElement::OnAutoRepeat  
 Met à jour l’élément de ruban en réponse à une entrée utilisateur soutenue.  
  
```  
virtual BOOL OnAutoRepeat();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode retourne toujours `FALSE`. Substituez cette méthode pour traiter l’entrée d’utilisateur soutenue.  
  
##  <a name="a-nameoncalctextsizea--cmfcribbonbaseelementoncalctextsize"></a><a name="oncalctextsize"></a>CMFCRibbonBaseElement::OnCalcTextSize  
 Calcule la taille du texte de l’élément de ruban.  
  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode pour calculer la taille du texte de l’élément de ruban.  
  
##  <a name="a-nameonchangemenuhighlighta--cmfcribbonbaseelementonchangemenuhighlight"></a><a name="onchangemenuhighlight"></a>CMFCRibbonBaseElement::OnChangeMenuHighlight  
 Appelé par l’infrastructure lorsque la sélection change pour un élément de ruban qui se trouve dans un menu.  
  
```  
virtual void OnChangeMenuHighlight(CMFCRibbonPanelMenuBar* pPanelMenuBar  
    CMFCRibbonBaseElement* pHot);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPanelMenuBar`  
 Ce paramètre n'est pas utilisé.  
  
 [in] `pHot`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode pour mettre à jour un élément de ruban qui se trouve dans un menu lorsque la sélection change.  
  
##  <a name="a-nameondrawa--cmfcribbonbaseelementondraw"></a><a name="ondraw"></a>CMFCRibbonBaseElement::OnDraw  
 Appelé par l'infrastructure pour dessiner l'élément de ruban.  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode dans une classe dérivée si vous souhaitez personnaliser le dessin d’un élément de ruban spécifique.  
  
##  <a name="a-nameondrawkeytipa--cmfcribbonbaseelementondrawkeytip"></a><a name="ondrawkeytip"></a>CMFCRibbonBaseElement::OnDrawKeyTip  
 Appelé par l’infrastructure pour dessiner la touche d’accès de l’élément de ruban.  
  
```  
virtual void OnDrawKeyTip(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bIsMenu);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Rectangle de limite pour la touche d’accès.  
  
 [in] `bIsMenu`  
 `TRUE`Si la touche d’accès est pour un bouton de menu contextuel ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondrawmenuimagea--cmfcribbonbaseelementondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFCRibbonBaseElement::OnDrawMenuImage  
 Appelé par l’infrastructure lors du dessin de l’image de menu pour l’élément de ruban.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Rectangle d’image de menu.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE` pour indiquer l’image a été dessinée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondrawonlista--cmfcribbonbaseelementondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonBaseElement::OnDrawOnList  
 Appelé par l’infrastructure pour dessiner l’élément de ruban dans une zone de liste de commandes.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique pour l’élément de ruban.  
  
 [in] `strText`  
 Le texte d’affichage.  
  
 [in] `nTextOffset`  
 Distance, en pixels, du côté gauche de la zone de liste pour afficher du texte.  
  
 [in] `rect`  
 Le rectangle d’affichage de l’élément de ruban.  
  
 [in] `bIsSelected`  
 Ce paramètre n'est pas utilisé.  
  
 [in] `bHighlighted`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Notes  
 La zone de liste de commandes affiche les éléments de ruban pour permettre aux utilisateurs de personnaliser la barre d’outils Accès rapide.  
  
##  <a name="a-nameonkeya--cmfcribbonbaseelementonkey"></a><a name="onkey"></a>CMFCRibbonBaseElement::OnKey  
 Appelé par l’infrastructure lorsque l’utilisateur appuie sur une touche d’accès et l’élément de ruban a le focus.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsMenuKey`  
 `TRUE`Si la touche d’accès affiche un menu contextuel. dans le cas contraire, `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’événement a été géré ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonmenukeya--cmfcribbonbaseelementonmenukey"></a><a name="onmenukey"></a>CMFCRibbonBaseElement::OnMenuKey  
 Appelé par l’infrastructure lorsque l’utilisateur appuie sur une touche d’accès menu sur le panneau principal.  
  
```  
virtual BOOL OnMenuKey(UINT nUpperChar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nUpperChar`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut cette méthode retourne toujours `FALSE`. Substituez cette méthode pour répondre lorsque l’utilisateur appuie sur une touche d’accès menu sur le panneau principal.  
  
##  <a name="a-nameonprocesskeya--cmfcribbonbaseelementonprocesskey"></a><a name="onprocesskey"></a>CMFCRibbonBaseElement::OnProcessKey  
 Appelé par l’infrastructure lorsque l’utilisateur appuie sur une touche de raccourci.  
  
```  
virtual BOOL OnProcessKey(UINT nChar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nChar`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode si vous souhaitez que l’élément de ruban pour traiter une touche de raccourci.  
  
##  <a name="a-nameonrtlchangeda--cmfcribbonbaseelementonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonBaseElement::OnRTLChanged  
 Appelé par l’infrastructure lorsque la disposition change de direction.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsRTL`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode pour ajuster l’élément ribbon lorsque la disposition change de direction. Le sens de la disposition par défaut est de gauche à droite.  
  
##  <a name="a-nameonsetfocusa--cmfcribbonbaseelementonsetfocus"></a><a name="onsetfocus"></a>CMFCRibbonBaseElement::OnSetFocus  
 Appelé par l’infrastructure lorsqu’un élément de ruban reçoit ou perd le focus d’entrée.  
  
```  
virtual void OnSetFocus(BOOL B);
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode dans une classe dérivée si vous souhaitez que votre application pour gérer une modification dans le focus d’un élément de ruban.  
  
##  <a name="a-nameonshowa--cmfcribbonbaseelementonshow"></a><a name="onshow"></a>CMFCRibbonBaseElement::OnShow  
 Appelé par l’infrastructure pour afficher ou masquer l’élément de ruban.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bShow`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode ne fait rien. Substituez cette méthode pour afficher ou masquer l’élément de ruban.  
  
##  <a name="a-nameonshowpopupmenua--cmfcribbonbaseelementonshowpopupmenu"></a><a name="onshowpopupmenu"></a>CMFCRibbonBaseElement::OnShowPopupMenu  
 Appelée par l’infrastructure avant que l’élément de ruban affiche un menu contextuel.  
  
```  
virtual void OnShowPopupMenu();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode avertit la fenêtre parente de la barre Ruban que l’élément de ruban affiche un menu contextuel.  
  
##  <a name="a-namepostmenucommanda--cmfcribbonbaseelementpostmenucommand"></a><a name="postmenucommand"></a>CMFCRibbonBaseElement::PostMenuCommand  
 Ferme le menu contextuel pour l’élément de ruban et envoie un message de fermeture au menu parent.  
  
```  
void PostMenuCommand(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdId`  
 Le paramètre n’est pas utilisé.  
  
### <a name="remarks"></a>Notes  
 Le message de fermeture est envoyé uniquement si l’élément de ruban se trouve sur le menu contextuel.  
  
##  <a name="a-nameredrawa--cmfcribbonbaseelementredraw"></a><a name="redraw"></a>CMFCRibbonBaseElement::Redraw  
 Met à jour l’affichage de l’élément de ruban.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode redessine le rectangle d’affichage de l’élément de ruban en appelant [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) avec la `RDW_INVALIDATE`, `RDW_ERASE`, et `RDW_UPDATENOW` indicateurs définis.  
  
##  <a name="a-namesetaccdataa--cmfcribbonbaseelementsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonBaseElement::SetACCData  
 Définit les données d’accessibilité de l’élément ruban.  
  
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
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode définit les données d’accessibilité de l’élément ruban et retourne toujours `TRUE`. Remplacez cette méthode pour définir l’accessibilité des données et retourner une valeur qui indique la réussite ou l’échec.  
  
##  <a name="a-namesetcompactmodea--cmfcribbonbaseelementsetcompactmode"></a><a name="setcompactmode"></a>CMFCRibbonBaseElement::SetCompactMode  
 Définit la taille d’affichage de l’élément de ruban.  
  
```  
virtual void SetCompactMode(BOOL bCompactMode = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bCompactMode`  
 `TRUE`Pour réduire la taille d’affichage de l’élément de ruban ; `FALSE` pour augmenter la taille d’affichage de l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
 Le tableau suivant résume la logique de cette méthode.  
  
|`bCompactMode`|Taille actuelle de l’élément du ruban|Nouvelle taille d’élément de ruban|  
|--------------------|---------------------------------|-----------------------------|  
|`TRUE`|Compact|Aucune modification.|  
|`TRUE`|Intermediate|Compact, s’il est possible.|  
|`TRUE`|Grande|Les intermédiaires si possible.|  
|`FALSE`|Compact|Les intermédiaires si possible ; dans le cas contraire volumineux.|  
  
##  <a name="a-namesetdataa--cmfcribbonbaseelementsetdata"></a><a name="setdata"></a>CMFCRibbonBaseElement::SetData  
 Associe un élément de données à l’élément de ruban.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwData`  
 La valeur de données.  
  
##  <a name="a-namesetdefaultmenulooka--cmfcribbonbaseelementsetdefaultmenulook"></a><a name="setdefaultmenulook"></a>CMFCRibbonBaseElement::SetDefaultMenuLook  
 Définit l’élément de ruban apparaisse comme une commande contextuelle.  
  
```  
void SetDefaultMenuLook(BOOL bIsDefaultMenuLook = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsDefaultMenuLook`  
 `TRUE`Pour définir l’élément de ruban apparaisse comme une commande contextuelle ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetdescriptiona--cmfcribbonbaseelementsetdescription"></a><a name="setdescription"></a>CMFCRibbonBaseElement::SetDescription  
 Définit la description de l'élément de ruban.  
  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszText`  
 Description de l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
 Le framework affiche la nouvelle description dans la barre d’état, ou dans l’info-bulle ou sous le bouton de menu.  
  
##  <a name="a-namesetida--cmfcribbonbaseelementsetid"></a><a name="setid"></a>CMFCRibbonBaseElement::SetID  
 Définit l’ID de commande de l’élément de ruban.  
  
```  
virtual void SetID(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 ID de la commande.  
  
##  <a name="a-namesetinitialmodea--cmfcribbonbaseelementsetinitialmode"></a><a name="setinitialmode"></a>CMFCRibbonBaseElement::SetInitialMode  
 Définit la taille d’affichage initial de l’élément de ruban.  
  
```  
virtual void SetInitialMode(BOOL bOneRow = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bOneRow`  
 `TRUE`Pour limiter la taille d’affichage de l’élément de ruban compresser ou intermédiaire ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 La taille d’affichage d’éléments de ruban peut être compact, intermédiaire ou de grande taille.  
  
##  <a name="a-namesetkeysa--cmfcribbonbaseelementsetkeys"></a><a name="setkeys"></a>CMFCRibbonBaseElement::SetKeys  
 Définit l’info-bulle pour l’élément de ruban.  
  
```  
virtual void SetKeys(
    LPCTSTR lpszKeys,  
    LPCTSTR lpszMenuKeys=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszKeys`  
 La touche d’accès de l’élément de ruban.  
  
 [in] `lpszMenuKeys`  
 La touche d’accès pour le menu contextuel de l’élément de ruban.  
  
##  <a name="a-namesetoriginala--cmfcribbonbaseelementsetoriginal"></a><a name="setoriginal"></a>CMFCRibbonBaseElement::SetOriginal  
 Définit l’élément de ruban d’origine pour l’élément de ruban.  
  
```  
virtual void SetOriginal(CMFCRibbonBaseElement* pOriginal);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pOriginal`  
 Pointeur vers un élément de ruban.  
  
### <a name="remarks"></a>Notes  
 Les éléments de ruban qui sont copiés vers un autre conteneur conservent un pointeur vers l’élément de ruban d’origine.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbaseelementsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonBaseElement::SetParentCategory  
 Définit la catégorie parente de l’élément de ruban.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParent`  
 Pointeur vers une catégorie de ruban.  
  
### <a name="remarks"></a>Notes  
 Les groupes d’onglets dans les contrôles de ruban sont appelés des catégories.  
  
##  <a name="a-namesetparentmenua--cmfcribbonbaseelementsetparentmenu"></a><a name="setparentmenu"></a>CMFCRibbonBaseElement::SetParentMenu  
 Définit le parent conteneur du menu de l’élément de ruban.  
  
```  
virtual void SetParentMenu(CMFCRibbonPanelMenuBar* pMenuBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMenuBar`  
 Le menu parent.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetparentribbonbara--cmfcribbonbaseelementsetparentribbonbar"></a><a name="setparentribbonbar"></a>CMFCRibbonBaseElement::SetParentRibbonBar  
 Définit la barre de ruban parent pour l’élément de ruban.  
  
```  
virtual void SetParentRibbonBar(CMFCRibbonBar* pRibbonBar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pRibbonBar`  
 Pointeur vers la barre de ruban parent.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetrecta--cmfcribbonbaseelementsetrect"></a><a name="setrect"></a>CMFCRibbonBaseElement::SetRect  
 Définit les dimensions du rectangle d’affichage de l’élément de ruban.  
  
```  
void SetRect(CRect rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rect`  
 Les dimensions du rectangle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettexta--cmfcribbonbaseelementsettext"></a><a name="settext"></a>CMFCRibbonBaseElement::SetText  
 Définit le texte et la touche d’accès de l’élément de ruban.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszText`  
 Le texte et la touche d’accès de l’élément de ruban.  
  
### <a name="remarks"></a>Remarques  
 Pour définir la touche d’accès de l’élément de ruban, ajoutez la séquence d’échappement de saut de ligne suivie par les caractères de la touche d’accès à `lpszText`.  
  
### <a name="example"></a>Exemple  
  
```  
//Set the text for the ribbon element  
SetText(_T("Margins"))  
//Set the text and a single-letter keytip  
SetText(_T("Margins\nm"))  
//Set the text and a multiple-letter keytip  
SetText(_T("Line Numbers\nln"))  
```  
  
##  <a name="a-namesettextalwaysonrighta--cmfcribbonbaseelementsettextalwaysonright"></a><a name="settextalwaysonright"></a>CMFCRibbonBaseElement::SetTextAlwaysOnRight  
 Définit le texte de l’élément de ruban à afficher sur la droite.  
  
```  
virtual void SetTextAlwaysOnRight(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 `TRUE`Pour afficher le texte sur la droite. dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesettooltiptexta--cmfcribbonbaseelementsettooltiptext"></a><a name="settooltiptext"></a>CMFCRibbonBaseElement::SetToolTipText  
 Définit le texte info-bulle pour l’élément de ruban.  
  
```  
virtual void SetToolTipText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszText`  
 Le texte info-bulle.  
  
##  <a name="a-namesetvisiblea--cmfcribbonbaseelementsetvisible"></a><a name="setvisible"></a>CMFCRibbonBaseElement::SetVisible  
 Définit la visibilité de l’élément de ruban.  
  
```  
void SetVisible(BOOL bIsVisible);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsVisible`  
 `TRUE`Pour afficher l’élément de ruban ; `FALSE` pour masquer l’élément de ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namestretchhorizontallya--cmfcribbonbaseelementstretchhorizontally"></a><a name="stretchhorizontally"></a>CMFCRibbonBaseElement::StretchHorizontally  
 Étend la largeur de l’élément de ruban.  
  
```  
virtual void StretchHorizontally();
```  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode génère un échec d’assertion dans les versions debug et ne doit donc pas être appelée. Substituez cette méthode pour s’étendre à la largeur de l’élément de ruban.  
  
##  <a name="a-namestretchtowholerowa--cmfcribbonbaseelementstretchtowholerow"></a><a name="stretchtowholerow"></a>CMFCRibbonBaseElement::StretchToWholeRow  
 Modifie la hauteur d’affichage de l’élément de ruban de la hauteur de ligne spécifiée.  
  
```  
virtual BOOL StretchToWholeRow(
    CDC* pDC,  
    int nHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Ce paramètre n'est pas utilisé.  
  
 [in] `nHeight`  
 La hauteur de la ligne.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la hauteur d’affichage a été définie ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode pour modifier la hauteur d’affichage de l’élément de ruban de la hauteur de ligne spécifiée.  
  
##  <a name="a-nameupdatetooltipinfoa--cmfcribbonbaseelementupdatetooltipinfo"></a><a name="updatetooltipinfo"></a>CMFCRibbonBaseElement::UpdateTooltipInfo  
 Met à jour le texte d’info-bulle à l’aide de la ressource de commande pour l’élément de ruban.  
  
```  
virtual void UpdateTooltipInfo();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namehasfocusa--cmfcribbonbaseelementhasfocus"></a><a name="hasfocus"></a>CMFCRibbonBaseElement::HasFocus  
 Indique si l’élément parent a le focus clavier.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le focus de l’élément de ruban ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

