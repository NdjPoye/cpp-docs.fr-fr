---
title: Classe de CMFCRibbonGallery | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonGallery
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonGallery class
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
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
ms.openlocfilehash: c4eadb9820f2d7318131cc4d197dbe28d65491c0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbongallery-class"></a>CMFCRibbonGallery (classe)
Implémente les galeries de ruban de style Office 2007.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](#cmfcribbongallery)|Construit et initialise un objet `CMFCRibbonGallery`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::AddGroup](#addgroup)|Ajoute un nouveau groupe dans la galerie.|  
|[CMFCRibbonGallery::AddSubItem](#addsubitem)|Ajoute un nouvel élément de menu au menu contextuel.|  
|[CMFCRibbonGallery::Clear](#clear)|Efface le contenu de la galerie.|  
|[CMFCRibbonGallery::EnableMenuResize](#enablemenuresize)|Active ou désactive le redimensionnement du volet de menu.|  
|[CMFCRibbonGallery::EnableMenuSideBar](#enablemenusidebar)|Active ou désactive la barre latérale à gauche du menu contextuel.|  
|[CMFCRibbonGallery::GetCompactSize](#getcompactsize)|(Substitue [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonGallery::GetDroppedDown](#getdroppeddown)|(Substitue [CMFCRibbonBaseElement::GetDroppedDown](../../mfc/reference/cmfcribbonbaseelement-class.md#getdroppeddown).)|  
|[CMFCRibbonGallery::GetGroupName](#getgroupname)|Retourne le nom du groupe qui se trouve à l’index spécifié.|  
|[CMFCRibbonGallery::GetGroupOffset](#getgroupoffset)||  
|[CMFCRibbonGallery::GetIconsInRow](#geticonsinrow)|Retourne le nombre d’éléments dans une ligne de la galerie du ruban.|  
|[CMFCRibbonGallery::GetItemToolTip](#getitemtooltip)|Retourne le texte d’info-bulle associé à un élément dans la galerie.|  
|[CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem)|Retourne l’index du dernier élément dans la bibliothèque de l’utilisateur sélectionné.|  
|[CMFCRibbonGallery::GetPaletteID](#getpaletteid)|Retourne l’ID de commande de la bibliothèque en cours.|  
|[CMFCRibbonGallery::GetRegularSize](#getregularsize)|(Substitue [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonGallery::GetSelectedItem](#getselecteditem)||  
|[CMFCRibbonGallery::HasMenu](#hasmenu)|(Substitue [CMFCRibbonButton::HasMenu](../../mfc/reference/cmfcribbonbutton-class.md#hasmenu).)|  
|[CMFCRibbonGallery::IsButtonMode](#isbuttonmode)|Spécifie si la galerie est contenue dans un bouton de la galerie.|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](#ismenuresizeenabled)|Spécifie si le redimensionnement de menu est activé ou désactivé.|  
|[CMFCRibbonGallery::IsMenuResizeVertical](#ismenuresizevertical)||  
|[CMFCRibbonGallery::IsMenuSideBar](#ismenusidebar)|Spécifie si la barre latérale est activée ou désactivée.|  
|[CMFCRibbonGallery::OnAfterChangeRect](#onafterchangerect)|(Substitue `CMFCRibbonButton::OnAfterChangeRect`.)|  
|[CMFCRibbonGallery::OnDraw](#ondraw)|(Substitue [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonGallery::OnEnable](#onenable)|(Substitue `CMFCRibbonBaseElement::OnEnable`.)|  
|[CMFCRibbonGallery::OnRTLChanged](#onrtlchanged)|(Substitue [CMFCRibbonBaseElement::OnRTLChanged](../../mfc/reference/cmfcribbonbaseelement-class.md#onrtlchanged).)|  
|[CMFCRibbonGallery::RedrawIcons](#redrawicons)|Redessine la galerie.|  
|[CMFCRibbonGallery::RemoveItemToolTips](#removeitemtooltips)|Supprime les info-bulles de tous les éléments de la galerie.|  
|[CMFCRibbonGallery::SelectItem](#selectitem)||  
|[CMFCRibbonGallery::SetACCData](#setaccdata)|(Substitue [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
|[CMFCRibbonGallery::SetButtonMode](#setbuttonmode)|Spécifie s’il faut afficher la galerie de ruban comme un bouton de liste déroulante ou une palette directement sur le ruban.|  
|[CMFCRibbonGallery::SetGroupName](#setgroupname)|Définit le nom d’un groupe.|  
|[CMFCRibbonGallery::SetIconsInRow](#seticonsinrow)|Définit le nombre d’éléments par ligne dans la galerie.|  
|[CMFCRibbonGallery::SetItemToolTip](#setitemtooltip)|Définit le texte info-bulle pour un élément dans la galerie.|  
|[CMFCRibbonGallery::SetPalette](#setpalette)|Attache une palette dans une galerie de ruban.|  
|[CMFCRibbonGallery::SetPaletteID](#setpaletteid)|Définit l’ID de commande qui est envoyé dans le `WM_COMMAND` de message quand un élément de la galerie a été sélectionné.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](#ondrawpaletteicon)|Appelé par l’infrastructure lorsqu’une icône de la galerie est dessinée.|  
  
## <a name="remarks"></a>Remarques  
 Un bouton de la galerie se comporte comme un bouton de menu classique, sauf qu’il affiche une galerie lorsqu’un utilisateur l’ouvre. Lorsque vous sélectionnez un élément dans une galerie, le framework envoie le `WM_COMMAND` message avec l’ID de commande du bouton. Lorsque vous gérez le message, vous devez appeler [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) pour déterminer quel élément a été sélectionné dans la galerie.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans le `CMFCRibbonGallery` classe pour configurer un `CMFCRibbonGallery` objet. L’exemple montre comment spécifier le nombre d’éléments par ligne dans la galerie, activer le redimensionnement du volet de menu, activer la barre latérale à gauche du menu contextuel et afficher la galerie de ruban comme une palette directement sur le ruban. Cet extrait de code fait partie de la [Client dessiner, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient n °&6;](../../mfc/reference/codesnippet/cpp/cmfcribbongallery-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonPaletteGallery.h  
  
##  <a name="a-nameaddgroupa--cmfcribbongalleryaddgroup"></a><a name="addgroup"></a>CMFCRibbonGallery::AddGroup  
 Ajoute un nouveau groupe dans la galerie.  
  
```  
void AddGroup(
    LPCTSTR lpszGroupName,  
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    CMFCToolBarImages& imagesGroup);

 
void AddGroup(
    LPCTSTR lpszGroupName,  
    int nIconsNum);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszGroupName`  
 Spécifie le nom du groupe.  
  
 [in] `uiImagesPaletteResID`  
 Spécifie l’ID de la liste d’images contenant les images pour le groupe de ressources.  
  
 [in] `cxPaletteImage`  
 Spécifie la largeur en pixels d’une image.  
  
 [in] `imagesGroup`  
 Une référence à la liste d’images contenant les images de groupe.  
  
 [in] `nIconsNum`  
 Spécifie le nombre d’icônes dans le groupe. Ce paramètre doit être spécifié uniquement pour personnalisé (owner-drawn) groupes.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez diviser les éléments dans une galerie de ruban en plusieurs groupes en appelant cette méthode. Chaque groupe peut avoir une légende.  
  
##  <a name="a-nameaddsubitema--cmfcribbongalleryaddsubitem"></a><a name="addsubitem"></a>CMFCRibbonGallery::AddSubItem  
 Ajoute un nouvel élément de menu au menu contextuel.  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1,  
    BOOL bOnTop=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pSubItem`  
 Pointeur vers l’élément à ajouter au menu.  
  
 [in] `nIndex`  
 Spécifie l’index de base zéro d’un emplacement où insérer l’élément.  
  
 [in] `bOnTop`  
 `TRUE`Pour spécifier que l’élément doit être inséré avant la galerie de ruban ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez combiner des galeries de fenêtre contextuelle avec les éléments de menu contextuel en appelant cette méthode. Éléments de menu peuvent être placés avant ou après la galerie.  
  
 Pour insérer l’élément avant de la galerie, définissez `bOnTop` à `TRUE`. Définissez `bOnTop` à `FALSE` pour insérer l’élément sous la galerie.  
  
> [!NOTE]
>  Le paramètre `nIndex` Spécifie l’index d’insertion en haut de la galerie et en bas de la galerie. Par exemple, si vous avez besoin d’insérer un élément à une position avant la galerie, définissez `nIndex` 1 et `bOnTop` à `TRUE`. De même, si vous avez besoin d’insérer un élément à une position au-dessous de la galerie, définissez `nIndex` 1 et `bOnTop` à `FALSE`.  
  
##  <a name="a-namecleara--cmfcribbongalleryclear"></a><a name="clear"></a>CMFCRibbonGallery::Clear  
 Efface le contenu de la galerie.  
  
```  
virtual void Clear();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour supprimer tout le contenu de la galerie de ruban. Ceci doit être fait avant d’attacher une nouvelle galerie de ruban ou un ensemble de groupes dans la galerie du ruban.  
  
##  <a name="a-namecmfcribbongallerya--cmfcribbongallerycmfcribbongallery"></a><a name="cmfcribbongallery"></a>CMFCRibbonGallery::CMFCRibbonGallery  
 Construit et initialise un [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md) objet.  
  
```  
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CMFCToolBarImages& imagesPalette);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    UINT uiImagesPaletteResID=0,  
    int cxPaletteImage=0);

 
CMFCRibbonGallery (
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    CSize sizeIcon,  
    int nIconsNum,  
    BOOL bDefaultButtonStyle=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Spécifie l’ID de commande de la commande à exécuter lorsqu’un utilisateur clique sur le bouton.  
  
 `lpszText`  
 Spécifie le texte affiché sur le bouton.  
  
 `nSmallImageIndex`  
 Index de base zéro de la petite image à afficher sur le bouton.  
  
 `nLargeImageIndex`  
 Index de base zéro de la grande image à afficher sur le bouton.  
  
 `imagesPalette`  
 Une référence à la [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) objet qui contient les images à afficher dans la galerie.  
  
 `uiImagesPaletteResID`  
 L’ID de ressource de la liste des images à afficher dans la galerie.  
  
 `cxPaletteImage`  
 Spécifie la largeur, en pixels, de l’image dans la galerie.  
  
 `sizeIcon`  
 Spécifie la taille, en pixels, de l’image de la galerie.  
  
 `nIconsNum`  
 Spécifie le nombre d’icônes dans la galerie.  
  
 `bDefaultButtonStyle`  
 Spécifie s’il faut utiliser la valeur par défaut ou le style de bouton owner-drawn.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameenablemenuresizea--cmfcribbongalleryenablemenuresize"></a><a name="enablemenuresize"></a>CMFCRibbonGallery::EnableMenuResize  
 Active ou désactive le redimensionnement du volet de menu.  
  
```  
void EnableMenuResize(
    BOOL bEnable = TRUE,  
    BOOL bVertcalOnly = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour activer le redimensionnement du menu ; dans le cas contraire, `FALSE`.  
  
 [in] `bVertcalOnly`  
 `TRUE`Pour spécifier que la galerie peut être redimensionnée uniquement verticalement ; `FALSE` pour spécifier que la galerie peut être redimensionné à la fois verticalement et horizontalement.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour activer ou désactiver le redimensionnement de la galerie du ruban. Lorsque le redimensionnement est activé, la galerie du ruban affiche une barre de redimensionnement qui permettent à un utilisateur pour la redimensionner.  
  
##  <a name="a-nameenablemenusidebara--cmfcribbongalleryenablemenusidebar"></a><a name="enablemenusidebar"></a>CMFCRibbonGallery::EnableMenuSideBar  
 Active ou désactive la barre latérale à gauche du menu contextuel.  
  
```  
void EnablMenuSideBar(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 `TRUE`Pour spécifier que la barre latérale est activée ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour activer ou désactiver la barre latérale de style Office XP sur le côté gauche du menu.  
  
##  <a name="a-namegetcompactsizea--cmfcribbongallerygetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonGallery::GetCompactSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetdroppeddowna--cmfcribbongallerygetdroppeddown"></a><a name="getdroppeddown"></a>CMFCRibbonGallery::GetDroppedDown  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CMFCRibbonBaseElement* GetDroppedDown();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetgroupnamea--cmfcribbongallerygetgroupname"></a><a name="getgroupname"></a>CMFCRibbonGallery::GetGroupName  
 Retourne le nom du groupe qui se trouve à l’index spécifié.  
  
```  
LPCTSTR GetGroupName(int nGroupIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nGroupIndex`  
 Spécifie l’index de base zéro pour le groupe dont vous souhaitez récupérer le nom.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom du groupe situé à l’index spécifié. En passant un index non valide provoque un échec d’assertion.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetgroupoffseta--cmfcribbongallerygetgroupoffset"></a><a name="getgroupoffset"></a>CMFCRibbonGallery::GetGroupOffset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int GetGroupOffset() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegeticonsinrowa--cmfcribbongallerygeticonsinrow"></a><a name="geticonsinrow"></a>CMFCRibbonGallery::GetIconsInRow  
 Retourne le nombre d’éléments dans une ligne de la galerie du ruban.  
  
```  
int GetIconsInRow() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans une ligne.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetitemtooltipa--cmfcribbongallerygetitemtooltip"></a><a name="getitemtooltip"></a>CMFCRibbonGallery::GetItemToolTip  
 Retourne le texte d’info-bulle associé à un élément dans la galerie.  
  
```  
LPCTSTR GetItemToolTip(int nItemIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nItemIndex`  
 Spécifie l’index de base zéro de l’élément pour lequel récupérer le texte info-bulle.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la chaîne d’info-bulle affecté à un élément dans la galerie du ruban. Il peut être `NULL` si aucune info-bulle n’est attribué à cet élément.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetlastselecteditema--cmfcribbongallerygetlastselecteditem"></a><a name="getlastselecteditem"></a>CMFCRibbonGallery::GetLastSelectedItem  
 Retourne l’index du dernier élément dans la galerie de ruban que l’utilisateur sélectionné.  
  
```  
static int GetLastSelectedItem(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdID`  
 Spécifie l’ID de commande de l’élément de menu qui a ouvert la galerie du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
 Lorsque l’utilisateur sélectionne un élément dans la galerie du ruban, la bibliothèque envoie le `WM_COMMAND` message ainsi que l’ID de commande du bouton de menu qui a ouvert la galerie du ruban.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetpaletteida--cmfcribbongallerygetpaletteid"></a><a name="getpaletteid"></a>CMFCRibbonGallery::GetPaletteID  
 Retourne l’ID de commande de la palette en cours.  
  
```  
int GetPaletteID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de la palette actuellement sélectionnée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetregularsizea--cmfcribbongallerygetregularsize"></a><a name="getregularsize"></a>CMFCRibbonGallery::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetselecteditema--cmfcribbongallerygetselecteditem"></a><a name="getselecteditem"></a>CMFCRibbonGallery::GetSelectedItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehasmenua--cmfcribbongalleryhasmenu"></a><a name="hasmenu"></a>CMFCRibbonGallery::HasMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisbuttonmodea--cmfcribbongalleryisbuttonmode"></a><a name="isbuttonmode"></a>CMFCRibbonGallery::IsButtonMode  
 Spécifie si la palette est contenue dans un bouton de la galerie.  
  
```  
BOOL IsButtonMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la palette est affichée comme un bouton de menu déroulant ; `FALSE` si la palette s’affiche directement sur le ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameismenuresizeenableda--cmfcribbongalleryismenuresizeenabled"></a><a name="ismenuresizeenabled"></a>CMFCRibbonGallery::IsMenuResizeEnabled  
 Spécifie si le redimensionnement de menu est activé.  
  
```  
BOOL IsMenuResizeEnabled() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le redimensionnement du menu a été activé ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameismenuresizeverticala--cmfcribbongalleryismenuresizevertical"></a><a name="ismenuresizevertical"></a>CMFCRibbonGallery::IsMenuResizeVertical  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsMenuResizeVertical() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameismenusidebara--cmfcribbongalleryismenusidebar"></a><a name="ismenusidebar"></a>CMFCRibbonGallery::IsMenuSideBar  
 Spécifie si la barre latérale est activée ou désactivée.  
  
```  
BOOL IsMenuSideBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la barre latérale de style Office XP est dessinée sur le côté gauche du menu contextuel. dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonafterchangerecta--cmfcribbongalleryonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonGallery::OnAfterChangeRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondrawa--cmfcribbongalleryondraw"></a><a name="ondraw"></a>CMFCRibbonGallery::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondrawpaletteicona--cmfcribbongalleryondrawpaletteicon"></a><a name="ondrawpaletteicon"></a>CMFCRibbonGallery::OnDrawPaletteIcon  
 Appelé par l’infrastructure lorsqu’une icône de la galerie est dessinée.  
  
```  
virtual void OnDrawPaletteIcon(
    CDC* pDC,  
    CRect rectIcon,  
    int nIconIndex,  
    CMFCRibbonGalleryIcon* pIcon,  
    COLORREF clrText);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique qui est utilisé pour le dessin.  
  
 [in] `rectIcon`  
 Spécifie le rectangle englobant de l’icône à dessiner.  
  
 [in] `nIconIndex`  
 Spécifie l’index de base zéro dans la liste d’images d’icônes de la galerie de l’icône à dessiner.  
  
 [in] `pIcon`  
 Pointeur vers l’icône qui est dessiné.  
  
 [in] `clrText`  
 Spécifie la couleur du texte de l’élément à dessiner.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez substituer cette méthode dans une classe dérivée pour personnaliser l’apparence d’une galerie de ruban.  
  
##  <a name="a-nameonenablea--cmfcribbongalleryonenable"></a><a name="onenable"></a>CMFCRibbonGallery::OnEnable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonrtlchangeda--cmfcribbongalleryonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonGallery::OnRTLChanged  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameredrawiconsa--cmfcribbongalleryredrawicons"></a><a name="redrawicons"></a>CMFCRibbonGallery::RedrawIcons  
 Redessine la galerie.  
  
```  
void RedrawIcons();
```  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction pour redessiner la galerie. Vous devez appeler cette méthode si vous avez modifié le contenu de la galerie lors de l’exécution.  
  
##  <a name="a-nameremoveitemtooltipsa--cmfcribbongalleryremoveitemtooltips"></a><a name="removeitemtooltips"></a>CMFCRibbonGallery::RemoveItemToolTips  
 Supprime les info-bulles de tous les éléments de la galerie.  
  
```  
void RemoveItemToolTips();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameselectitema--cmfcribbongalleryselectitem"></a><a name="selectitem"></a>CMFCRibbonGallery::SelectItem  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SelectItem(int nItemIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nItemIndex`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetaccdataa--cmfcribbongallerysetaccdata"></a><a name="setaccdata"></a>CMFCRibbonGallery::SetACCData  
 Remplit l’objet `CAccessibilityData` spécifié avec des données d’accessibilité à partir de la galerie du ruban.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,   
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pParent`  
 La fenêtre parente de la fenêtre de la galerie du ruban.  
  
 [out] `data`  
 Un objet `CAccessibilityData` qui reçoit les données d’accessibilité de la galerie du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 `TRUE` si la méthode réussit ; sinon, `FALSE`.  
  
##  <a name="a-namesetbuttonmodea--cmfcribbongallerysetbuttonmode"></a><a name="setbuttonmode"></a>CMFCRibbonGallery::SetButtonMode  
 Détermine s’il faut afficher la galerie de ruban comme un bouton de liste déroulante ou une palette directement sur le ruban.  
  
```  
void SetButtonMode(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 `TRUE`Pour afficher la galerie du ruban comme un bouton de menu déroulant ; `FALSE` pour afficher le contenu de la galerie de ruban directement sur le ruban.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetgroupnamea--cmfcribbongallerysetgroupname"></a><a name="setgroupname"></a>CMFCRibbonGallery::SetGroupName  
 Définit le nom d’un groupe.  
  
```  
void SetGroupName(
    int nGroupIndex,  
    LPCTSTR lpszGroupName);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nGroupIndex`  
 Spécifie l’index de base zéro pour le groupe pour lequel le nom est en cours de modification.  
  
 [in] `lpszGroupName`  
 Spécifie le nouveau nom pour le groupe.  
  
### <a name="remarks"></a>Notes  
 Le groupe dont le nom est en cours de modification doit avoir été ajouté à l’aide de la [CMFCRibbonGallery::AddGroup](#addgroup) (méthode).  
  
##  <a name="a-nameseticonsinrowa--cmfcribbongalleryseticonsinrow"></a><a name="seticonsinrow"></a>CMFCRibbonGallery::SetIconsInRow  
 Spécifie le nombre d’éléments par ligne dans la galerie.  
  
```  
void SetIconsInRow(int nIconsInRow);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIconsInRow`  
 Spécifie le nombre d’éléments à afficher dans chaque ligne de la galerie.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour spécifier la largeur de la galerie du ruban.  
  
##  <a name="a-namesetitemtooltipa--cmfcribbongallerysetitemtooltip"></a><a name="setitemtooltip"></a>CMFCRibbonGallery::SetItemToolTip  
 Définit le texte info-bulle pour un élément dans la galerie.  
  
```  
void SetItemToolTip(
    int nItemIndex,  
    LPCTSTR lpszToolTip);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nItemIndex`  
 Index de base zéro de l’élément de palette auquel associer l’info-bulle.  
  
 [in] `lpszToolTip`  
 Texte à afficher sur l’info-bulle.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetpalettea--cmfcribbongallerysetpalette"></a><a name="setpalette"></a>CMFCRibbonGallery::SetPalette  
 Attache une palette dans une galerie de ruban.  
  
```  
void SetPalette(CMFCToolBarImages& imagesPalette);

 
void SetPalette(
    UINT uiImagesPaletteResID,  
    int cxPaletteImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `imagesPalette`  
 Spécifie la liste d’images qui contient les icônes qui apparaissent sur la galerie.  
  
 [in] `uiImagesPaletteResID`  
 Spécifie l’ID de ressource de la liste d’images qui contient les icônes qui apparaissent sur la galerie.  
  
 [in] `cxPaletteImage`  
 Spécifie la largeur, en pixels, d’une image dans la galerie.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetpaletteida--cmfcribbongallerysetpaletteid"></a><a name="setpaletteid"></a>CMFCRibbonGallery::SetPaletteID  
 Définit l’ID de commande qui est envoyé dans le **WM_COMMAND** message lorsqu’un utilisateur sélectionne un élément de la galerie.  
  
```  
void SetPaletteID(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 Spécifie l’ID de commande qui est envoyé dans le **WM_COMMAND** message lorsqu’un utilisateur sélectionne un élément de la galerie.  
  
### <a name="remarks"></a>Notes  
 Pour déterminer l’élément spécifique qu’un utilisateur a sélectionnés à partir de la galerie, appelez le [CMFCRibbonGallery::GetLastSelectedItem](#getlastselecteditem) méthode statique.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton (classe)](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton (classe)](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

