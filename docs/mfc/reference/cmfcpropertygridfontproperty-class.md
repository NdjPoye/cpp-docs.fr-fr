---
title: Classe de CMFCPropertyGridFontProperty | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty::OnClickButton method
- CMFCPropertyGridFontProperty class
- CMFCPropertyGridFontProperty::FormatProperty method
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 05d1db7e7de2ee72244e885d8a083ac3cda20142
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty (classe)
La `CMFCPropertyGridFileProperty` classe prend en charge un élément de contrôle de liste de propriétés qui ouvre une boîte de dialogue de sélection de police.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Construit un objet `CMFCPropertyGridFontProperty`.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Met en forme la représentation textuelle d'une valeur de propriété. (Substitue [CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Récupère la couleur de police que l’utilisateur sélectionne dans la boîte de dialogue Police.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Récupère la police que l’utilisateur sélectionne dans la boîte de dialogue Police.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Appelé par l'infrastructure quand l'utilisateur clique sur un bouton contenu dans une propriété. (Substitue [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Notes  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 Construit un objet `CMFCPropertyGridFontProperty`.  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `strName`  
 Nom de la propriété.  
  
 [in] `lf`  
 Une structure de police logique qui spécifie les attributs de la police.  
  
 [in] `dwFontDialogFlags`  
 Styles sont appliqués à la boîte de dialogue Police qui s’affiche lorsque vous cliquez sur le bouton de liste déroulante de valeur de propriété. La valeur par défaut est la combinaison d’opérations de bits (OR) de CF_EFFECTS et CF_SCREENFONTS. Pour plus d’informations, consultez la `Flags` paramètre de la [CHOOSEFONT Structure](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] `lpszDescr`  
 Description de la propriété de police. La valeur par défaut est `NULL`.  
  
 [in] `dwData`  
 Données spécifiques à l’application, tel qu’un entier ou un pointeur à d’autres données qui sont associés à la propriété. La valeur par défaut est 0.  
  
 [in] `color`  
 La couleur de la police. La valeur par défaut est la couleur par défaut.  
  
### <a name="remarks"></a>Remarques  
 Un `CMFCPropertyGridFontProperty` objet représente une propriété de police dans un contrôle de police de grille de propriétés.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCPropertyGridFontProperty` classe. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#26;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 Récupère la couleur de police que l’utilisateur sélectionne dans la boîte de dialogue Police.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur de couleur RVB qui représente la couleur de police sélectionnée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 Récupère la police que l’utilisateur sélectionne dans la boîte de dialogue Police.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure qui décrit la police sélectionnée.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl (classe)](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty (classe)](../../mfc/reference/cmfcpropertygridproperty-class.md)

