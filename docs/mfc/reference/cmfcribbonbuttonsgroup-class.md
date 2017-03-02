---
title: Classe de CMFCRibbonButtonsGroup | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButtonsGroup
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButtonsGroup class
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
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
ms.openlocfilehash: 2d8909ca63bd1d9121e1126d46a08312521cc4ac
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup, Classe
La `CMFCRibbonButtonsGroup` classe vous permet d’organiser un ensemble de boutons de ruban dans un groupe. Tous les boutons du groupe sont directement adjacents horizontalement et placés dans une bordure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Construit un objet `CMFCRibbonButtonsGroup`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonButtonsGroup::AddButton](#addbutton)|Ajoute un bouton à un groupe.|  
|[CMFCRibbonButtonsGroup::AddButtons](#addbuttons)|Ajoute une liste de boutons à un groupe.|  
|[CMFCRibbonButtonsGroup::GetButton](#getbutton)|Retourne un pointeur vers le bouton qui se trouve à l’index spécifié.|  
|[CMFCRibbonButtonsGroup::GetCount](#getcount)|Retourne le nombre de boutons dans le groupe.|  
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Retourne la taille d’image des images normales dans le groupe de ruban (remplace [CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize).)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Retourne la taille standard de l’élément de ruban (remplace [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Rapports si le `CMFCRibbonButtonsGroup` objet contient des images de barre d’outils.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Dessine l’image appropriée pour un bouton spécifié, selon que le bouton est normal, en surbrillance ou désactivé.|  
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|Supprime tous les boutons de la `CMFCRibbonButtonsGroup` objet.|  
|[CMFCRibbonButtonsGroup::SetImages](#setimages)|Affecte au groupe des images.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Définit le parent `CMFCRibbonCategory` de la `CMFCRibbonButtonsGroup` objet et tous les boutons qu’il contient (remplace [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory).)|  
  
## <a name="remarks"></a>Notes  
 Le groupe est dérivé de [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) et peuvent être manipulées comme une seule entité. Vous pouvez placer le groupe sur n’importe quel panneau de configuration ou un menu contextuel.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCRibbonButtonsGroup` classe. L’exemple montre comment construire un `CMFCRibbonButtonsGroup` de l’objet, assigner des images pour le groupe de boutons de ruban et ajoutez un bouton au groupe de boutons de ruban. Cet extrait de code fait partie de la [Client dessiner, exemple](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient n °&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonbuttonsgroup.h  
  
##  <a name="a-nameaddbuttona--cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>CMFCRibbonButtonsGroup::AddButton  
 Ajoute un bouton à un groupe.  
  
```  
void AddButton(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pButton`  
 Pointeur vers un bouton Ajouter.  
  
##  <a name="a-nameaddbuttonsa--cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>CMFCRibbonButtonsGroup::AddButtons  
 Ajoute une liste de boutons à un groupe.  
  
```  
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lstButtons`  
 Une liste de pointeurs vers les boutons que vous souhaitez ajouter.  
  
##  <a name="a-namecmfcribbonbuttonsgroupa--cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup  
 Construit un objet `CMFCRibbonButtonsGroup`.  
  
```  
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pButton`  
 Spécifie un bouton pour ajouter à la nouvelle `CMFCRibbonButtonsGroup` objet.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetbuttona--cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>CMFCRibbonButtonsGroup::GetButton  
 Retourne un pointeur vers le bouton qui se trouve à l’index spécifié.  
  
```  
CMFCRibbonBaseElement* GetButton(int i) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `i`  
 Index de base zéro d’un bouton à retourner.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le bouton situé à l’index spécifié. `NULL`Si l’index spécifié est hors limites.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetcounta--cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>CMFCRibbonButtonsGroup::GetCount  
 Retourne le nombre de boutons dans le groupe.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de boutons dans le groupe.  
  
##  <a name="a-namegetimagesizea--cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>CMFCRibbonButtonsGroup::GetImageSize  
 Récupère la taille de l’image source de la méthode protégée `CMFCToolBarImages` membre `m_Images`.  
  
```  
const CSize GetImageSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la taille de l’image source des images de barre d’outils, le cas échéant, ou un `CSize` de zéro dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetregularsizea--cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonButtonsGroup::GetRegularSize  
 Récupère la taille maximale possible de l’élément de groupe de ruban.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique du groupe du ruban.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehasimagesa--cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>CMFCRibbonButtonsGroup::HasImages  
 Rapports si le `CMFCRibbonButtonsGroup` objet contient des images de barre d’outils.  
  
```  
BOOL HasImages() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si la méthode protégée `CMFCToolBarImages` membre `m_Images` contient toutes les images, ou FALSE si non.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameondrawimagea--cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>CMFCRibbonButtonsGroup::OnDrawImage  
 Dessine l’image appropriée pour un bouton spécifié, selon que le bouton est normal, en surbrillance ou désactivé.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rectImage,  
    CMFCRibbonBaseElement* pButton,  
    int nImageIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers le contexte de périphérique de la `CMFCRibbonButtonsGroup` objet.  
  
 [in] `rectImage`  
 Le rectangle dans lequel dessiner l’image.  
  
 [in] `pButton`  
 Le bouton pour lequel dessiner l’image.  
  
 [in] `nImageIndex`  
 Index de l’image à dessiner sur le bouton (dans un des trois tableaux des boutons normaux, mis en surbrillance ou désactivés).  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameremovealla--cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>CMFCRibbonButtonsGroup::RemoveAll  
 Supprime tous les boutons de la `CMFCRibbonButtonsGroup` objet.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetimagesa--cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>CMFCRibbonButtonsGroup::SetImages  
 Affecte des images pour le groupe de boutons de ruban.  
  
```  
void SetImages(
    CMFCToolBarImages* pImages,  
    CMFCToolBarImages* pHotImages,  
    CMFCToolBarImages* pDisabledImages);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pImages`  
 Les images.  
  
 [in] `pHotImages`  
 Images interactives.  
  
 [in] `pDisabledImages`  
 Images désactivés.  
  
### <a name="remarks"></a>Notes  
 Appelez `SetImages` avant d’ajouter des boutons à un groupe. Le nombre d’images doit être supérieur ou égal au nombre de boutons à ajouter au groupe.  
  
> [!NOTE]
>  Images interactives sont des images qui sont affichent lorsque l’utilisateur pointe sur le bouton. Images désactivés sont des images qui sont affichent lorsque le bouton est désactivé.  
  
##  <a name="a-namesetparentcategorya--cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>CMFCRibbonButtonsGroup::SetParentCategory  
 Définit le parent `CMFCRibbonCategory` de la `CMFCRibbonButtonsGroup` objet et tous les boutons qu’il contient.  
  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pCategory`  
 Pointeur vers la catégorie parente pour définir (les groupes d’onglets dans les contrôles de ruban sont appelées catégories).  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

