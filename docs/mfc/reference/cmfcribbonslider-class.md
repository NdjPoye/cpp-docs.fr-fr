---
title: Classe de CMFCRibbonSlider | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider class
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
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
ms.openlocfilehash: 9f05ae7d0f3e1775a3321928867471749e11e679
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider (classe)
La `CMFCRibbonSlider` classe implémente un contrôle slider que vous pouvez ajouter à une barre de ruban ou la barre d’état du ruban. Le contrôle Slider de ruban ressemble aux curseurs de zoom présents dans les applications Office 2007.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Construit et initialise un contrôle slider de ruban.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Retourne la position actuelle du curseur.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Retourne la valeur maximale du curseur.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Retourne la valeur minimale du curseur.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Retourne la taille normale de l'élément de ruban. (Substitue [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Retourne la taille de l’incrément de zoom du contrôle slider.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Spécifie si le curseur comporte des boutons de zoom.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Appelé par l'infrastructure pour dessiner l'élément de ruban. (Substitue [CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Définit la position actuelle du curseur.|  
|[CMFCRibbonSlider::SetRange](#setrange)|Spécifie la plage du contrôle slider en définissant les valeurs minimales et maximales.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Affiche ou masque les boutons de zoom.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Définit la taille de l’incrément de zoom du contrôle slider.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez utiliser la `SetRange` méthode pour configurer la plage de zoom est incrémentée pour le curseur. Vous pouvez définir la position actuelle du curseur à l’aide de la `SetPos` méthode.  
  
 Vous pouvez afficher les boutons de zoom circulaire à gauche et à droite du contrôle slider à l’aide de la `SetZoomButtons` méthode. Par défaut, le curseur est horizontal, le bouton Zoom sur la gauche affiche un signe moins et le bouton zoom de droite affiche un signe plus (+).  
  
 Le `SetZoomIncrement` méthode définit l’incrément à ajouter ou à soustraire de la position actuelle lorsqu’un utilisateur clique sur les boutons de zoom.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans la `CMFCRibbonSlider` classe pour définir les propriétés du curseur. L’exemple montre comment construire un `CMFCRibbonSlider` de l’objet, afficher les boutons de zoom, définir la position actuelle du curseur et la plage de valeurs pour le contrôle de curseur.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#12;](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxribbonslider.h  
  
##  <a name="a-namecmfcribbonslidera--cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider  
 Construire un curseur de ruban.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 ID de curseur.  
  
 [in]. `nWidth`  
 Largeur du curseur en pixels.  
  
### <a name="remarks"></a>Remarques  
 Construit un curseur de ruban est `nWidth` pixels de large dans la catégorie du Panneau de configuration dans lequel le curseur est ajouté. Par défaut, le curseur est horizontal.  
  
##  <a name="a-namegetposa--cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFCRibbonSlider::GetPos  
 Retourne la position actuelle du curseur.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La position actuelle du curseur, qui correspond à une position par rapport au début du curseur.  
  
##  <a name="a-namegetrangemaxa--cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax  
 Obtient l’incrément maximal du curseur qui le curseur peut voyager sur le contrôle slider.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’incrément maximal du curseur qui le curseur peut voyager sur le contrôle slider.  
  
##  <a name="a-namegetrangemina--cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin  
 Retourne l’incrément minimale que le curseur peut voyager sur le contrôle slider.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’incrément minimum que le curseur peut voyager sur le contrôle slider.  
  
##  <a name="a-namegetregularsizea--cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetzoomincrementa--cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement  
 Obtenir l’incrément de zoom du contrôle slider.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’incrément de zoom du contrôle slider.  
  
##  <a name="a-namehaszoombuttonsa--cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons  
 Spécifie si le curseur comporte des boutons de zoom.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le curseur comporte des boutons de zoom ; `FALSE` dans le cas contraire.  
  
##  <a name="a-nameondrawa--cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetposa--cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCRibbonSlider::SetPos  
 Définir la position actuelle du curseur.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nPos`  
 Spécifie la position à définir pour le curseur. La position est par rapport au début du curseur.  
  
 [in] `bRedraw`  
 Si `TRUE`, le curseur est redessiné.  
  
##  <a name="a-namesetrangea--cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCRibbonSlider::SetRange  
 Définir la plage de valeurs pour le contrôle de curseur.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nMin`  
 Spécifie la valeur minimale du contrôle slider.  
  
 [in] `nMax`  
 Spécifie la valeur maximale du contrôle slider.  
  
### <a name="remarks"></a>Notes  
 Spécifie la plage de valeurs pour le contrôle de curseur en définissant les valeurs minimales et maximales.  
  
##  <a name="a-namesetzoombuttonsa--cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons  
 Afficher ou masquer les boutons de zoom.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in]. `bSet`  
 `TRUE`Pour afficher les boutons de zoom ; `FALSE` pour les masquer.  
  
##  <a name="a-namesetzoomincrementa--cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement  
 Définissez l’incrément de zoom du contrôle slider.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nZoomIncrement`  
 Spécifie l’incrément de zoom du contrôle slider.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement (classe)](../../mfc/reference/cmfcribbonbaseelement-class.md)

