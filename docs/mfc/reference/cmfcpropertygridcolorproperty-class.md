---
title: Classe de CMFCPropertyGridColorProperty | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty class
- CMFCPropertyGridColorProperty::OnClickButton method
- CMFCPropertyGridColorProperty::FormatProperty method
- CMFCPropertyGridColorProperty::OnDrawValue method
- CMFCPropertyGridColorProperty::OnUpdateValue method
- CMFCPropertyGridColorProperty::OnEdit method
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
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
ms.openlocfilehash: 7069e35a44dbb0dbd4ad8d5d2b9156ccfbc15c76
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty (classe)
La classe `CMFCPropertyGridColorProperty` prend en charge un élément de contrôle de liste de propriétés qui ouvre une boîte de dialogue de sélection de couleur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Construit un objet `CMFCPropertyGridColorProperty`.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Permet la *automatique* bouton dans la boîte de dialogue de sélection de couleur. (Le bouton automatique standard est intitulé **automatique**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Permet la *autres* bouton dans la boîte de dialogue de sélection de couleur. (La norme autre bouton est intitulé **couleurs supplémentaires... **.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Met en forme la représentation textuelle d'une valeur de propriété. (Substitue [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Obtient la couleur actuelle de la propriété.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Appelé par l'infrastructure quand l'utilisateur clique sur un bouton contenu dans une propriété. (Substitue [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Appelé par l'infrastructure pour afficher la valeur de propriété. (Substitue [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Appelé par l'infrastructure quand l'utilisateur s'apprête à modifier une valeur de propriété. (Substitue [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Appelé par l'infrastructure quand la valeur d'une propriété modifiable a changé. (Substitue [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Définit une nouvelle couleur pour la propriété.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Spécifie le nombre de colonnes de la grille de propriétés de couleur actuelle.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Définit la valeur d'origine d'une propriété modifiable.|  
  
## <a name="remarks"></a>Remarques  
 La classe `CMFCPropertyGridColorProperty` prend en charge une propriété de couleur qui peut être ajoutée à un contrôle de liste de propriétés. Pour plus d’informations, consultez la [CMFCPropertyGridCtrl classe](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment construire un objet de la classe `CMFCPropertyGridColorProperty` et configurer cet objet à l'aide de différentes méthodes de la classe `CMFCPropertyGridColorProperty`. Le code explique comment activer les boutons automatique et autre et comment définir la couleur et le nombre de colonnes. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#13;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxpropertygridctrl.h  
  
##  <a name="a-namecmfcpropertygridcolorpropertya--cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 Construit un objet `CMFCPropertyGridColorProperty`.  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `strName`  
 Nom de la propriété.  
  
 [in] `color`  
 La valeur de la propriété de couleur.  
  
 [in] `pPalette`  
 Pointeur vers une palette de couleurs. La valeur par défaut est `NULL`.  
  
 [in] `lpszDescr`  
 La description de la propriété. La valeur par défaut est `NULL`.  
  
 [in] `dwData`  
 Données spécifiques à l’application, tel qu’un entier ou un pointeur à d’autres données qui sont associés à la propriété. La valeur par défaut est 0.  
  
##  <a name="a-nameenableautomaticbuttona--cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton  
 Permet la *automatique* bouton dans la boîte de dialogue de sélection de couleur. (Le bouton automatique standard est intitulé **automatique**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Le texte de l’étiquette du bouton automatique.  
  
 [in] `colorAutomatic`  
 La valeur de couleur RVB de la couleur automatique (par défaut).  
  
 [in] `bEnable`  
 `TRUE`Pour activer le bouton automatique ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameenableotherbuttona--cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton  
 Permet la *autres* bouton dans la boîte de dialogue de sélection de couleur. (La norme autre bouton est intitulé **couleurs supplémentaires... **.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Le texte de l’étiquette de l’autre bouton.  
  
 [in] `bAltColorDlg`  
 `TRUE`Pour afficher les `CMFCColorDialog` boîte de dialogue. `FALSE` pour afficher la boîte de dialogue de sélection de couleurs standard. La valeur par défaut est `TRUE`.  
  
 [in] `bEnable`  
 `TRUE`Pour afficher le bouton d’autres ; dans le cas contraire, `FALSE`.  La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetcolora--cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor  
 Obtient la couleur actuelle de la propriété.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de couleur RVB.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetcolora--cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor  
 Définit une nouvelle couleur pour la propriété.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 Une valeur de couleur RVB.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetcolumnsnumbera--cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber  
 Spécifie le nombre de colonnes de la grille de propriétés de couleur actuelle.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nColumnsNumber`  
 Le nombre de colonnes dans la grille de propriétés de couleur souhaité.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode définit la valeur de la `m_nColumnsNumber` protégé de membre de données.  
  
##  <a name="a-namesetoriginalvaluea--cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue  
 Définit la valeur d'origine d'une propriété modifiable.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `varValue`  
 Valeur.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) méthode pour réinitialiser la valeur d’origine d’une propriété modifiée.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl (classe)](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty (classe)](../../mfc/reference/cmfcpropertygridproperty-class.md)

