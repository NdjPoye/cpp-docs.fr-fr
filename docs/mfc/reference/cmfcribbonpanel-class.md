---
title: Classe de CMFCRibbonPanel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::CMFCRibbonPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::Add
- AFXRIBBONPANEL/CMFCRibbonPanel::AddSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::AddToolBar
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByData
- AFXRIBBONPANEL/CMFCRibbonPanel::FindByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCaptionHeight
- AFXRIBBONPANEL/CMFCRibbonPanel::GetCount
- AFXRIBBONPANEL/CMFCRibbonPanel::GetData
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDefaultButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetDroppedDown
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElement
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElements
- AFXRIBBONPANEL/CMFCRibbonPanel::GetElementsByID
- AFXRIBBONPANEL/CMFCRibbonPanel::GetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::GetGalleryRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::GetIndex
- AFXRIBBONPANEL/CMFCRibbonPanel::GetItemIDsList
- AFXRIBBONPANEL/CMFCRibbonPanel::GetName
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentButton
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentCategory
- AFXRIBBONPANEL/CMFCRibbonPanel::GetParentMenuBar
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPreferedMenuLocation
- AFXRIBBONPANEL/CMFCRibbonPanel::GetPressed
- AFXRIBBONPANEL/CMFCRibbonPanel::GetRect
- AFXRIBBONPANEL/CMFCRibbonPanel::GetVisibleElements
- AFXRIBBONPANEL/CMFCRibbonPanel::HasElement
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTest
- AFXRIBBONPANEL/CMFCRibbonPanel::HitTestEx
- AFXRIBBONPANEL/CMFCRibbonPanel::Insert
- AFXRIBBONPANEL/CMFCRibbonPanel::InsertSeparator
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::IsCollapsed
- AFXRIBBONPANEL/CMFCRibbonPanel::IsHighlighted
- AFXRIBBONPANEL/CMFCRibbonPanel::IsJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMainPanel
- AFXRIBBONPANEL/CMFCRibbonPanel::IsMenuMode
- AFXRIBBONPANEL/CMFCRibbonPanel::MakeGalleryItemVisible
- AFXRIBBONPANEL/CMFCRibbonPanel::OnKey
- AFXRIBBONPANEL/CMFCRibbonPanel::RecalcWidths
- AFXRIBBONPANEL/CMFCRibbonPanel::Remove
- AFXRIBBONPANEL/CMFCRibbonPanel::RemoveAll
- AFXRIBBONPANEL/CMFCRibbonPanel::Replace
- AFXRIBBONPANEL/CMFCRibbonPanel::ReplaceByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetCenterColumnVert
- AFXRIBBONPANEL/CMFCRibbonPanel::SetData
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementMenu
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTC
- AFXRIBBONPANEL/CMFCRibbonPanel::SetElementRTCByID
- AFXRIBBONPANEL/CMFCRibbonPanel::SetFocused
- AFXRIBBONPANEL/CMFCRibbonPanel::SetJustifyColumns
- AFXRIBBONPANEL/CMFCRibbonPanel::SetKeys
- AFXRIBBONPANEL/CMFCRibbonPanel::ShowPopup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonPanel class
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
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
ms.openlocfilehash: 1f833e1fa59f733734da321718d5db73377fa4bd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonpanel-class"></a>CMFCRibbonPanel (classe)
Implémente un panneau qui contient un jeu d'éléments de ruban. Lorsque le panneau est dessiné, il affiche le plus d'éléments possible, selon la taille du panneau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](#cmfcribbonpanel)|Construit et initialise un objet `CMFCRibbonPanel`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonPanel::Add](#add)|Ajoute un élément de ruban dans le panneau.|  
|[CMFCRibbonPanel::AddSeparator](#addseparator)|Ajoute un séparateur au volet du ruban.|  
|[CMFCRibbonPanel::AddToolBar](#addtoolbar)|Ajoute une barre d’outils dans le panneau de ruban.|  
|[CMFCRibbonPanel::FindByData](#findbydata)||  
|[CMFCRibbonPanel::FindByID](#findbyid)|Retourne un élément identifié par un ID de commande spécifié.|  
|[CMFCRibbonPanel::GetCaptionHeight](#getcaptionheight)||  
|[CMFCRibbonPanel::GetCount](#getcount)|Retourne le nombre d’éléments dans le volet du ruban.|  
|[CMFCRibbonPanel::GetData](#getdata)|Retourne les données définies par l’utilisateur associées au panneau.|  
|[CMFCRibbonPanel::GetDefaultButton](#getdefaultbutton)||  
|[CMFCRibbonPanel::GetDroppedDown](#getdroppeddown)||  
|[CMFCRibbonPanel::GetElement](#getelement)|Retourne l’élément de ruban situé à un index spécifié.|  
|[CMFCRibbonPanel::GetElements](#getelements)|Récupère tous les éléments qui figurent dans le volet du ruban.|  
|[CMFCRibbonPanel::GetElementsByID](#getelementsbyid)||  
|[CMFCRibbonPanel::GetFocused](#getfocused)|Retourne un élément qui a le focus.|  
|[CMFCRibbonPanel::GetGalleryRect](#getgalleryrect)|Retourne un rectangle englobant de l’élément de la galerie.|  
|[CMFCRibbonPanel::GetHighlighted](#gethighlighted)||  
|[CMFCRibbonPanel::GetIndex](#getindex)||  
|[CMFCRibbonPanel::GetItemIDsList](#getitemidslist)||  
|[CMFCRibbonPanel::GetName](#getname)||  
|[CMFCRibbonPanel::GetParentButton](#getparentbutton)||  
|[CMFCRibbonPanel::GetParentCategory](#getparentcategory)|Retourne la catégorie parente du volet du ruban.|  
|[CMFCRibbonPanel::GetParentMenuBar](#getparentmenubar)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](#getpreferedmenulocation)||  
|[CMFCRibbonPanel::GetPressed](#getpressed)||  
|[CMFCRibbonPanel::GetRect](#getrect)||  
|[CMFCRibbonPanel::GetVisibleElements](#getvisibleelements)|Obtient un tableau d’éléments visibles.|  
|[CMFCRibbonPanel::HasElement](#haselement)||  
|[CMFCRibbonPanel::HitTest](#hittest)||  
|[CMFCRibbonPanel::HitTestEx](#hittestex)||  
|[CMFCRibbonPanel::Insert](#insert)|Insère un élément de ruban à la position donnée.|  
|[CMFCRibbonPanel::InsertSeparator](#insertseparator)|Insère un séparateur à la position donnée.|  
|[CMFCRibbonPanel::IsCenterColumnVert](#iscentercolumnvert)|Spécifie si tous les éléments du Panneau de configuration doivent être centrées (alignement) verticalement par colonne.|  
|[CMFCRibbonPanel::IsCollapsed](#iscollapsed)||  
|[CMFCRibbonPanel::IsHighlighted](#ishighlighted)||  
|[CMFCRibbonPanel::IsJustifyColumns](#isjustifycolumns)|Spécifie si toutes les colonnes du panneau ont la même largeur.|  
|[CMFCRibbonPanel::IsMainPanel](#ismainpanel)||  
|[CMFCRibbonPanel::IsMenuMode](#ismenumode)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](#makegalleryitemvisible)|Fait défiler la galerie pour afficher l’élément de ruban spécifié.|  
|[CMFCRibbonPanel::OnKey](#onkey)||  
|[CMFCRibbonPanel::RecalcWidths](#recalcwidths)||  
|[CMFCRibbonPanel::Remove](#remove)|Supprime et éventuellement un élément situé à l’index spécifié.|  
|[CMFCRibbonPanel::RemoveAll](#removeall)|Supprime tous les éléments du Panneau de ruban.|  
|[CMFCRibbonPanel::Replace](#replace)|Remplace un élément par un autre en fonction de leurs valeurs d’index respectifs.|  
|[CMFCRibbonPanel::ReplaceByID](#replacebyid)|Remplace un élément avec un autre basé sur un ID de commande spécifié.|  
|[CMFCRibbonPanel::SetCenterColumnVert](#setcentercolumnvert)|Commandes du panneau pour aligner les éléments verticalement par colonne.|  
|[CMFCRibbonPanel::SetData](#setdata)|Données définies par l’utilisateur associe avec le volet du ruban.|  
|[CMFCRibbonPanel::SetElementMenu](#setelementmenu)|Assigne un menu contextuel à l’élément qui possède l’ID de commande donné.|  
|[CMFCRibbonPanel::SetElementRTC](#setelementrtc)|Ajoute un élément de ruban spécifié par les informations de classe d’exécution fournis au volet du ruban.|  
|[CMFCRibbonPanel::SetElementRTCByID](#setelementrtcbyid)|Ajoute un élément de ruban spécifié par les informations de classe d’exécution fournis au volet du ruban.|  
|[CMFCRibbonPanel::SetFocused](#setfocused)|Définit le focus sur l’élément de ruban spécifié.|  
|[CMFCRibbonPanel::SetJustifyColumns](#setjustifycolumns)|Active ou désactive la justification de la colonne.|  
|[CMFCRibbonPanel::SetKeys](#setkeys)|Définit le raccourci clavier qui affiche le volet du ruban.|  
|[CMFCRibbonPanel::ShowPopup](#showpopup)||  
  
## <a name="remarks"></a>Remarques  
 Volets de ruban sont des groupements logiques de tâches associées que vous créez dans les catégories de ruban. Comme la taille de la modification du ruban, la disposition du panneau s’ajuste automatiquement pour afficher les éléments autant que possible.  
  
 Vous pouvez obtenir un ruban panneaux qui se trouve dans une catégorie de ruban en appelant le [CMFCRibbonCategory::GetPanel](../../mfc/reference/cmfcribboncategory-class.md#getpanel) (méthode).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer un `CMFCRibbonPanel` à l’aide de différentes méthodes dans la `CMFCRibbonPanel` classe. L’exemple montre comment définir le raccourci clavier qui affiche le volet du ruban, aligner les éléments dans le panneau verticalement par colonne et activer la justification de la colonne. Cet extrait de code fait partie de la [exemple de démonstration de MS Office 2007](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#10;](../../mfc/reference/codesnippet/cpp/cmfcribbonpanel-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonPanel.h  
  
##  <a name="add"></a>CMFCRibbonPanel::Add  
 Ajoute l’élément de ruban spécifié dans le tableau des éléments de ruban qui est contenu dans le volet du ruban.  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `pElem`  
 Pointeur vers un élément de ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="addseparator"></a>CMFCRibbonPanel::AddSeparator  
 Ajoute un séparateur au volet du ruban.  
  
```  
virtual void AddSeparator();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour ajouter un séparateur dans le volet du ruban. Le séparateur apparaît en regard de l’élément de ruban qui a été ajouté par l’appel précédent à [CMFCRibbonPanel::Add](#add). Pour insérer un séparateur à une position donnée, appelez [CMFCRibbonPanel::InsertSeparator](#insertseparator).  
  
##  <a name="addtoolbar"></a>CMFCRibbonPanel::AddToolBar  
 Ajoute une barre d’outils dans le panneau de ruban.  
  
```  
CMFCRibbonButtonsGroup* AddToolBar(
UINT uiToolbarResID,  
UINT uiColdResID = 0,  
UINT uiHotResID = 0,  
UINT uiDisabledResID = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiToolbarResID`  
 Spécifie l’ID de ressource de la barre d’outils à ajouter.  
  
 [in] `uiColdResID`  
 Spécifie l’ID de ressource d’images à froid de la barre d’outils.  
  
 [in] `uiHotResID`  
 Spécifie l’ID de ressource d’images à chaud de la barre d’outils.  
  
 [in] `uiDisabledResID`  
 Spécifie l’ID de ressource d’images désactivé de la barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Appelez cette méthode pour ajouter une barre d’outils dans le volet du ruban. La barre d’outils apparaît en regard de l’élément de ruban ajouté par l’appel précédent à [CMFCRibbonPanel::Add](#add).  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur les barres d’outils, images interactives, les images à froid et images désactivés, consultez [CMFCToolBar classe](../../mfc/reference/cmfctoolbar-class.md).  
  
##  <a name="cmfcribbonpanel"></a>CMFCRibbonPanel::CMFCRibbonPanel  
 Construit et initialise un [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md) objet.  
  
```  
CMFCRibbonPanel(
LPCTSTR lpszName = NULL,  
HICON hIcon = NULL);  
  
CMFCRibbonPanel(CMFCRibbonGallery* pPaletteButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszName`  
 Nom du volet du ruban.  
  
 [in] `hIcon`  
 Handle de l’icône du bouton par défaut pour le volet du ruban.  
  
 [in] `pPaletteButton`  
 Pointeur vers une galerie de ruban pour le volet du ruban.  
  
##  <a name="findbydata"></a>CMFCRibbonPanel::FindByData  
 Récupère l’élément de ruban qui est associé avec les données spécifiées.  
  
```  
CMFCRibbonBaseElement* FindByData(DWORD_PTR dwData) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwData`  
 Les données associées à un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un élément de ruban si la méthode a réussi ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="findbyid"></a>CMFCRibbonPanel::FindByID  
 Récupère l’élément de ruban qui est identifié par l’ID de commande spécifié.  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 L’ID de commande d’un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément de ruban qui est identifiée par l’ID de la commande spécifiée ; dans le cas contraire `NULL` si aucun élément du ruban n’est identifiée par l’ID de commande spécifié.  
  
##  <a name="getcaptionheight"></a>CMFCRibbonPanel::GetCaptionHeight  
 Récupère la hauteur d’une légende pour le volet du ruban.  
  
```  
int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur, en pixels, d’une légende pour le volet du ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getcount"></a>CMFCRibbonPanel::GetCount  
 Récupère le nombre d’éléments de ruban qui sont contenus dans le volet du ruban.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments de ruban qui sont contenus dans le volet du ruban.  
  
##  <a name="getdata"></a>CMFCRibbonPanel::GetData  
 Retourne les données définies par l’utilisateur associées au panneau.  
  
```  
DWORD_PTR GetData() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les données définies par l’utilisateur associées au panneau.  
  
##  <a name="getdefaultbutton"></a>CMFCRibbonPanel::GetDefaultButton  
 Récupère le bouton par défaut pour le volet du ruban.  
  
```  
CMFCRibbonButton& GetDefaultButton();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le bouton par défaut pour le volet du ruban.  
  
### <a name="remarks"></a>Remarques  
 Le bouton par défaut s’affiche lorsqu’un panneau de ruban est insuffisante pour afficher ses éléments de ruban.  
  
##  <a name="getdroppeddown"></a>CMFCRibbonPanel::GetDroppedDown  
 Récupère un pointeur vers un élément de ruban s’est déroulée son menu contextuel.  
  
```  
CMFCRibbonBaseElement* GetDroppedDown() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément de ruban qui a son menu contextuel supprimé dans le cas contraire `NULL` si aucun élément de ruban n’a son menu contextuel déroulée.  
  
### <a name="remarks"></a>Remarques  
 Uniquement les éléments de ruban qui sont contenus dans le volet du ruban sont testés.  
  
##  <a name="getelement"></a>CMFCRibbonPanel::GetElement  
 Retourne l’élément de ruban situé à un index spécifié.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro de l’élément à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers l’élément ribbon base situé à la position `nIndex` dans le volet du ruban, ou `NULL` s’il n’existe aucun élément à l’index spécifié.  
  
##  <a name="getelements"></a>CMFCRibbonPanel::GetElements  
 Récupère tous les éléments de ruban qui sont contenus dans le volet du ruban.  
  
```  
void GetElements(CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `arElements`  
 Tableau à remplir avec tous les éléments de ruban qui sont contenus dans le volet du ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getelementsbyid"></a>CMFCRibbonPanel::GetElementsByID  
 Ajoute les éléments de ruban ayant l’ID de commande spécifiée dans le tableau spécifié.  
  
```  
void GetElementsByID(
UINT uiCmdID,  
CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 ID de commande pour un élément de ruban.  
  
 [in] `arElements`  
 Tableau d’éléments de ruban.  
  
### <a name="remarks"></a>Remarques  
 Uniquement les éléments de ruban qui sont contenus dans le volet du ruban sont testés.  
  
##  <a name="gethighlighted"></a>CMFCRibbonPanel::GetHighlighted  
 Récupère l’élément de ruban est mis en surbrillance dans le volet du ruban.  
  
```  
CMFCRibbonBaseElement* GetHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément ribbon qui est mis en surbrillance dans le volet du ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getindex"></a>CMFCRibbonPanel::GetIndex  
 Récupère l’index de base zéro de l’élément spécifié de ruban à partir du tableau d’éléments de ruban qui sont contenus dans le volet du ruban.  
  
```  
virtual int GetIndex(CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElem`  
 Pointeur vers un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément de ruban spécifié si la méthode a réussi ; sinon -1.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getitemidslist"></a>CMFCRibbonPanel::GetItemIDsList  
 Récupère l’ID de commande pour tous les éléments de ruban dans le volet du ruban.  
  
```  
void GetItemIDsList(CList<UINT, UINT>& lstItems) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `lstItems`  
 La liste des ID de commande pour les éléments de ruban qui sont contenus dans le volet du ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getname"></a>CMFCRibbonPanel::GetName  
 Récupère le nom du Panneau de ruban.  
  
```  
LPCTSTR GetName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nom du volet du ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getparentbutton"></a>CMFCRibbonPanel::GetParentButton  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* GetParentButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getparentcategory"></a>CMFCRibbonPanel::GetParentCategory  
 Retourne la catégorie parente du volet du ruban.  
  
```  
CMFCRibbonCategory* GetParentCategory() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la catégorie de ruban qui contient ce panneau de ruban.  
  
##  <a name="getparentmenubar"></a>CMFCRibbonPanel::GetParentMenuBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonPanelMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getpreferedmenulocation"></a>CMFCRibbonPanel::GetPreferedMenuLocation  
 Récupère le rectangle d’affichage par défaut pour le menu contextuel du volet du ruban.  
  
```  
virtual BOOL GetPreferedMenuLocation(CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rect`  
 Ce paramètre n'est pas utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne toujours la valeur `FALSE`. Substituez cette méthode pour récupérer le rectangle d’affichage par défaut pour le menu contextuel du volet du ruban.  
  
##  <a name="getpressed"></a>CMFCRibbonPanel::GetPressed  
 Récupère un pointeur vers un élément de ruban dans le volet du ruban si actuellement, l’utilisateur appuie dessus.  
  
```  
CMFCRibbonBaseElement* GetPressed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un élément de ruban si l’utilisateur appuie sur actuellement dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getrect"></a>CMFCRibbonPanel::GetRect  
 Récupère le rectangle d’affichage pour le panneau de ruban.  
  
```  
const CRect& GetRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rectangle d’affichage pour le panneau de ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="haselement"></a>CMFCRibbonPanel::HasElement  
 Indique si le volet du ruban contient l’élément spécifié du ruban.  
  
```  
BOOL HasElement(const CMFCRibbonBaseElement* pElem) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pElem`  
 Pointeur vers un élément de ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le volet du ruban contient l’élément spécifié de ruban ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="highlight"></a>CMFCRibbonPanel::Highlight  
 Définit la couleur de surbrillance pour le volet du ruban sélectionné et l’élément de ruban spécifié par le point.  
  
```  
virtual void Highlight(
BOOL bHighlight,  
CPoint point);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bHighlight`  
 `TRUE`Pour mettre en évidence le volet du ruban ; `FALSE` à unhighlight le volet du ruban.  
  
 [in] `point`  
 Les coordonnées x et y du pointeur, par rapport à l’angle supérieur gauche de la fenêtre.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="hittest"></a>CMFCRibbonPanel::HitTest  
 Récupère un élément de ruban si le point spécifié se trouve dans celui-ci.  
  
```  
virtual CMFCRibbonBaseElement* HitTest(
CPoint point,  
BOOL bCheckPanelCaption = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Les coordonnées x et y du pointeur, par rapport à l’angle supérieur gauche de la fenêtre.  
  
 [in] `bCheckPanelCaption`  
 `TRUE`Pour tester la légende du Panneau de ruban ; dans le cas contraire `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un élément de ruban si le point spécifié se trouve dans dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Remarques  
 Uniquement les éléments de ruban qui sont contenus dans le volet du ruban sont testés.  
  
##  <a name="hittestex"></a>CMFCRibbonPanel::HitTestEx  
 Récupère l’index de base zéro de l’élément de ruban qui a le point spécifié qu’il contient.  
  
```  
virtual int HitTestEx(CPoint point) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `point`  
 Les coordonnées x et y du pointeur, par rapport à l’angle supérieur gauche de la fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’élément de ruban qui a le point spécifié est situé dans sinon -1.  
  
### <a name="remarks"></a>Notes  
 Uniquement les éléments de ruban qui sont contenus dans le volet du ruban sont testés.  
  
##  <a name="insert"></a>CMFCRibbonPanel::Insert  
 Insère l’élément ribbon spécifié à la position spécifiée du tableau d’éléments de ruban qui est contenue dans le volet du ruban.  
  
```  
virtual BOOL Insert(
CMFCRibbonBaseElement* pElem,  
int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `pElem`  
 Pointeur vers un élément de ruban.  
  
 [in] `nIndex`  
 Valeur de base zéro, comprise entre -1 et le nombre d’éléments de ruban qui sont contenus dans le tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban a été insérée avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de `nIndex` -1, ou si `nIndex` est égal au nombre d’éléments de ruban dans le tableau, l’élément de ruban spécifié est ajouté à la fin du tableau. Si la valeur de `nIndex` est hors plage, la méthode échoue.  
  
##  <a name="insertseparator"></a>CMFCRibbonPanel::InsertSeparator  
 Insère un séparateur à la position donnée.  
  
```  
virtual BOOL InsertSeparator(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro où le séparateur est inséré.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le séparateur a été ajoutée avec succès ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour insérer un séparateur à la position spécifiée par `nIndex`. Pour insérer un séparateur en regard de l’élément de ruban ajoutée récemment, appelez [CMFCRibbonPanel::AddSeparator](#addseparator).  
  
##  <a name="iscentercolumnvert"></a>CMFCRibbonPanel::IsCenterColumnVert  
 Indique si les positions verticales des éléments du ruban sont centrées dans leur rectangle d’affichage.  
  
```  
BOOL IsCenterColumnVert() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si vertical positionne des éléments de ruban sont centrés dans leur rectangle d’affichage ; dans le cas contraire `FALSE`.  
  
##  <a name="iscollapsed"></a>CMFCRibbonPanel::IsCollapsed  
 Indique si la taille d’affichage du volet du ruban est réduite dans le sens horizontal.  
  
```  
BOOL IsCollapsed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la taille d’affichage du volet du ruban est réduite dans le sens horizontal ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’un ruban est réduit, il affiche uniquement le bouton par défaut, son nom et une flèche de déroulement.  
  
##  <a name="ishighlighted"></a>CMFCRibbonPanel::IsHighlighted  
 Indique si l’affichage du volet du ruban est mis en surbrillance.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’affichage du volet du ruban est mis en surbrillance ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 L’affichage d’un panneau de ruban est mis en surbrillance lorsque le pointeur est sur lui.  
  
##  <a name="isjustifycolumns"></a>CMFCRibbonPanel::IsJustifyColumns  
 Indique si les dimensions de l’affichage d’éléments de ruban qui se trouvent dans la même colonne dans le volet du ruban sont définies à la même largeur.  
  
```  
BOOL IsJustifyColumns() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les dimensions de l’affichage d’éléments de ruban qui se trouvent dans la même colonne dans le volet du ruban sont définis sur la même largeur ; dans le cas contraire `FALSE`.  
  
##  <a name="ismainpanel"></a>CMFCRibbonPanel::IsMainPanel  
 Indique si le volet du ruban est le volet du ruban principal.  
  
```  
virtual BOOL IsMainPanel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne toujours la valeur `FALSE`. Substituez cette méthode pour indiquer si le volet du ruban est le volet du ruban principal.  
  
 Le volet du ruban principal s’affiche lorsque l’utilisateur sélectionne l’application.  
  
##  <a name="ismenumode"></a>CMFCRibbonPanel::IsMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="onkey"></a>CMFCRibbonPanel::OnKey  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nChar`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="recalcwidths"></a>CMFCRibbonPanel::RecalcWidths  
 Recalcule la largeur de chaque configuration de mise en page d’affichage pour le volet du ruban.  
  
```  
virtual void RecalcWidths(
CDC* pDC,  
int nHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique pour le volet du ruban.  
  
 [in] `nHeight`  
 Hauteur du volet du ruban.  
  
### <a name="remarks"></a>Remarques  
 Un panneau de ruban change de configuration de mise en page lors du changement de largeur disponible.  
  
##  <a name="remove"></a>CMFCRibbonPanel::Remove  
 Supprime et éventuellement un élément situé à l’index spécifié.  
  
```  
BOOL Remove(
int nIndex,  
BOOL bDelete = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro de l’élément est supprimé du Panneau de ruban.  
  
 [in] `bDelete`  
 `TRUE`Pour supprimer l’élément en cours de suppression ; dans le cas contraire, `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément a été supprimé et supprimé (si `bDelete` est `TRUE`) ; `FALSE` si l’élément n’a pas été supprimé ou s’il existe aucun élément de ruban ne situé à `nIndex`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour supprimer un élément du Panneau de ruban.  
  
##  <a name="removeall"></a>CMFCRibbonPanel::RemoveAll  
 Supprime tous les éléments de ruban à partir du Panneau de ruban.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarques  
 Tous les éléments de ruban sont supprimés à partir du Panneau de ruban et détruits.  
  
##  <a name="replace"></a>CMFCRibbonPanel::Replace  
 Remplace un élément par un autre en fonction de leur valeur d’index.  
  
```  
BOOL Replace(
int nIndex,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro de l’élément à remplacer.  
  
 [in] [out]`pElem`  
 Un pointeur valide vers l’élément qui remplace l’élément d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban d’origine a été remplacé avec succès par le nouvel élément de ruban ; `FALSE` si l’élément de ruban n’a pas été remplacée ou s’il n’existe aucun élément à l’index spécifié.  
  
### <a name="remarks"></a>Remarques  
 Pour remplacer un élément de ruban par ID de commande, exécutez [CMFCRibbonPanel::ReplaceByID](#replacebyid).  
  
##  <a name="replacebyid"></a>CMFCRibbonPanel::ReplaceByID  
 Remplace un élément avec un autre basé sur un ID de commande spécifié.  
  
```  
BOOL ReplaceByID(
UINT uiCmdID,  
CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Spécifie l’ID de commande de l’élément à remplacer.  
  
 [in] [out]`pElem`  
 Un pointeur valide vers l’élément qui remplacera l’élément d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’élément de ruban d’origine a été remplacé avec succès par le nouvel élément de ruban ; `FALSE` si l’élément de ruban n’a pas été remplacée ou si aucun élément avec l’ID de commande spécifié n’existe réellement.  
  
### <a name="remarks"></a>Remarques  
 Pour remplacer un élément de ruban en fonction de la position, appelez [CMFCRibbonPanel::Replace](#replace).  
  
##  <a name="setcentercolumnvert"></a>CMFCRibbonPanel::SetCenterColumnVert  
 Active ou désactive le centrage des positions verticales d’éléments de ruban dans leur rectangle d’affichage.  
  
```  
void SetCenterColumnVert(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 `TRUE`Pour centrer les positions verticales des éléments de ruban dans leur rectangle d’affichage ; `FALSE` pour désactiver cette fonctionnalité.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setdata"></a>CMFCRibbonPanel::SetData  
 Données définies par l’utilisateur associe avec le volet du ruban.  
  
```  
void SetData(DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `dwData`  
 Spécifie les données définies par l’utilisateur à définir.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour associer des données définies par l’utilisateur avec le volet du ruban.  
  
##  <a name="setelementmenu"></a>CMFCRibbonPanel::SetElementMenu  
 Assigne un menu contextuel à l’élément qui possède l’ID de commande donné.  
  
```  
BOOL SetElementMenu(
UINT uiCmdID,  
HMENU hMenu,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);

 
BOOL SetElementMenu(
UINT uiCmdID,  
UINT uiMenuResID,  
BOOL bIsDefautCommand = FALSE,  
BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Spécifie l’ID de commande de l’élément de ruban où le menu est ajouté.  
  
 [in] `hMenu`  
 Spécifie le handle vers le menu Windows à ajouter au volet du ruban.  
  
 [in] `bIsDefautCommand`  
 `TRUE`Pour spécifier que la commande associée à l’élément de ruban doit être exécutée si l’utilisateur clique sur l’élément de ruban. Dans ce cas, le menu est ouvert uniquement lorsque l’utilisateur clique sur la flèche en regard de l’élément de ruban. `FALSE`Pour spécifier que la commande associée à l’élément de ruban ne doit pas être exécutée si l’utilisateur clique sur l’élément de ruban. Dans ce cas, le menu contextuel s’affiche quelle que soit l’endroit où l’utilisateur clique sur l’élément.  
  
 [in] `bRightAlign`  
 `TRUE`Pour spécifier que le menu contextuel est aligné à droite ; dans le cas contraire, `FALSE`.  
  
 [in] `uiMenuResID`  
 Spécifie l’ID de ressource du menu à ajouter au volet du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le menu a été attribué à l’élément de ruban ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour affecter un menu contextuel pour l’élément de ruban qui a l’ID de commande donné.  
  
##  <a name="setelementrtc"></a>CMFCRibbonPanel::SetElementRTC  
 Ajoute l’élément de ruban qui est spécifié par les informations de classe d’exécution fournis au volet du ruban.  
  
```  
CMFCRibbonBaseElement* SetElementRTC(
int nIndex,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Spécifie l’index de base zéro de l’élément de ruban à ajouter.  
  
 [in] [out]`pRTC`  
 Pointeur vers les informations de classe d’exécution de l’élément de ruban est ajouté au volet du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément de ruban qui a été créé en utilisant les informations de la classe runtime spécifié.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez ajouter un élément personnalisé (par exemple, un bouton de couleur) au volet du ruban, vous devez spécifier les informations de classe d’exécution de l’élément personnalisé. Le ruban stocke ces informations, crée l’élément personnalisé et remplace un élément existant qui se trouve (identifié par) ID de commande spécifié. Le ruban puis retourne un pointeur vers l’élément qui vient d’être créé.  
  
##  <a name="setelementrtcbyid"></a>CMFCRibbonPanel::SetElementRTCByID  
 Ajoute un élément de ruban qui est spécifié par les informations de classe d’exécution fournis au volet du ruban.  
  
```  
CMFCRibbonBaseElement* SetElementRTCByID(
UINT uiCmdID,  
CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Spécifie l’ID de commande de l’élément de ruban à ajouter.  
  
 [in] [out]`pRTC`  
 Pointeur vers les informations de classe d’exécution associés à l’élément de ruban est ajouté au volet du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément de ruban qui a été créé en utilisant les informations de la classe runtime spécifié.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez ajouter un élément personnalisé (par exemple, un bouton de couleur) au volet du ruban, vous devez spécifier les informations de classe d’exécution de l’élément personnalisé. Le ruban stocke ces informations, crée l’élément personnalisé et remplace un élément situé à l’ID de commande spécifié. Ensuite, il retourne un pointeur vers l’élément qui vient d’être créé.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `SetElementRTCByID` méthode :  
  
```  
 
// Load and add toolbar with standard buttons. This toolbar  
// should display a custom color button with id ID_CHAR_COLOR:  
 
pPanel->AddToolBar(IDR_MAINFRAME,
    IDB_MAINFRAME256);

CMFCRibbonColorButton* pColorButton = 
(CMFCRibbonColorButton*)pPanel->SetElementRTCByID(
ID_CHAR_COLOR,
    RUNTIME_CLASS (CMFCRibbonColorButton));

 
// SetElementRTCByID sets runtime class and returns a pointer  
// to the newly created custom button,
    which can be set up immediately:  
pColorButton->EnableAutomaticButton(_T("Automatic"),
    RGB (0,
    0,
    0));  
```  
  
##  <a name="setjustifycolumns"></a>CMFCRibbonPanel::SetJustifyColumns  
 Active ou désactive l’ajustement de la largeur des éléments de ruban dans la même colonne.  
  
```  
void SetJustifyColumns(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 `TRUE`Pour ajuster la largeur des éléments de ruban dans la même colonne à la largeur du plus grand élément du ruban dans la colonne ; `FALSE` pour désactiver cet ajustement de la largeur.  
  
### <a name="remarks"></a>Remarques  
 Lorsque cette fonctionnalité est activée dans un panneau de ruban, la largeur des éléments de ruban dans la même colonne est ajustée à la largeur du plus grand élément du ruban dans la même colonne.  
  
##  <a name="setkeys"></a>CMFCRibbonPanel::SetKeys  
 Définit la touche d’accès pour le bouton par défaut du volet du ruban.  
  
```  
void SetKeys(LPCTSTR lpszKeys);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszKeys`  
 La touche d’accès pour le bouton par défaut du volet du ruban.  
  
### <a name="remarks"></a>Remarques  
 Le bouton par défaut s’affiche lorsqu’un panneau de ruban est insuffisante pour afficher ses éléments de ruban.  
  
##  <a name="showpopup"></a>CMFCRibbonPanel::ShowPopup  
 Crée et affiche un menu déroulant dans le volet du ruban.  
  
```  
CMFCRibbonPanelMenu* ShowPopup(CMFCRibbonDefaultPanelButton* pButton = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pButton`  
 Pointeur vers le bouton par défaut pour le volet du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le menu contextuel pour le volet du ruban si la méthode a réussi ; dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Notes  
 Le menu contextuel pour le volet du ruban est disponible uniquement lorsque l’affichage du volet du ruban est réduit.  
  
##  <a name="setfocused"></a>CMFCRibbonPanel::SetFocused  
 Définit le focus sur l’élément de ruban spécifié.  
  
```  
void SetFocused(CMFCRibbonBaseElement* pNewFocus);
```  
  
### <a name="parameters"></a>Paramètres  
 `pNewFocus`  
 Pointeur vers un élément de ruban qui reçoit le focus.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="makegalleryitemvisible"></a>CMFCRibbonPanel::MakeGalleryItemVisible  
 Fait défiler la galerie pour afficher l’élément de ruban spécifié.  
  
```  
void MakeGalleryItemVisible(CMFCRibbonBaseElement* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers un élément de ruban à afficher.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="iswindows7look"></a>CMFCRibbonPanel::IsWindows7Look  
 Indique si le ruban parent a Windows 7 Rechercher (bouton petite application rectangulaire).  
  
```  
BOOL IsWindows7Look() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le ruban parent compose Windows 7 de recherche ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getvisibleelements"></a>CMFCRibbonPanel::GetVisibleElements  
 Récupère un tableau d’éléments visibles.  
  
```  
void GetVisibleElements(
CArray<CMFCRibbonBaseElement*,  
CMFCRibbonBaseElement*>& arElements);
```  
  
### <a name="parameters"></a>Paramètres  
 `arElements`  
 Lorsque la fonction retourne une valeur, ce paramètre contient un tableau d’éléments visibles.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getgalleryrect"></a>CMFCRibbonPanel::GetGalleryRect  
 Retourne un rectangle englobant d’un élément de la galerie.  
  
```  
CRect GetGalleryRect();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Taille et la position de l’élément de galerie dans ce panneau.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getfocused"></a>CMFCRibbonPanel::GetFocused  
 Retourne un élément qui a le focus.  
  
```  
CMFCRibbonBaseElement* GetFocused() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un élément ayant le focus ou `NULL`.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Classe de CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement (classe)](../../mfc/reference/cmfcribbonbaseelement-class.md)
