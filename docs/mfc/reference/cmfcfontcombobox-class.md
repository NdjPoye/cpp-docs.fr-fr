---
title: Classe de CMFCFontComboBox | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox::DrawItem method
- CMFCFontComboBox::PreTranslateMessage method
- CMFCFontComboBox::MeasureItem method
- CMFCFontComboBox class
- CMFCFontComboBox::CompareItem method
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
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
ms.openlocfilehash: 1252f5ca102637e70cc384afd723464aec4144b4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox (classe)
La `CMFCFontComboBox` classe crée un contrôle de zone de liste déroulante qui contient une liste de polices.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Construit un objet `CMFCFontComboBox`.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Appelé par l’infrastructure pour déterminer la position relative d’un nouvel élément dans la zone de liste triée du contrôle de zone de liste déroulante police actuelle. (Substitue [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Appelé par l’infrastructure pour dessiner un élément spécifié dans le contrôle de zone de liste déroulante police actuelle. (Substitue [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Récupère des informations sur la police actuellement sélectionnée.|  
|`CMFCFontComboBox::MeasureItem`|Appelé par l’infrastructure d’informer Windows des dimensions de la zone de liste dans le contrôle de zone de liste déroulante police actuelle. (Substitue [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Sélectionne la police qui correspond aux critères spécifiés dans la zone de liste déroulante de police.|  
|[CMFCFontComboBox::Setup](#setup)|Initialise la liste des éléments dans la zone de liste déroulante de police.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Indique à l’infrastructure de la police à utiliser pour dessiner les étiquettes d’élément dans la zone de liste déroulante de police actuelle.|  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser un `CMFCFontComboBox` de l’objet dans une boîte de dialogue, ajoutez un `CMFCFontComboBox` variable à la classe de boîte de dialogue. Ensuite, dans le `OnInitDialog` méthode de la classe de boîte de dialogue, appel la [CMFCFontComboBox::Setup](#setup) méthode pour initialiser la liste des éléments dans le contrôle de zone de liste déroulante.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxfontcombobox.h  
  
##  <a name="a-namecmfcfontcomboboxa--cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox  
 Construit un objet `CMFCFontComboBox`.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetselfonta--cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>CMFCFontComboBox::GetSelFont  
 Récupère des informations sur la police actuellement sélectionnée.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers [CMFCFontInfo classe](../../mfc/reference/cmfcfontinfo-class.md) objet qui décrit une police. Il peut être `NULL` si aucune police n’est sélectionnée dans la zone de liste déroulante.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namembdrawusingfonta--cmfcfontcomboboxmbdrawusingfont"></a><a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont  
 Indique à l’infrastructure de la police à utiliser pour dessiner les étiquettes d’élément dans la zone de liste déroulante de police actuelle.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Remarques  
 Affecter à ce membre `TRUE` pour diriger l’infrastructure d’utiliser la même police pour dessiner chaque étiquette de l’élément. Affecter à ce membre `FALSE` pour diriger l’infrastructure pour dessiner chaque étiquette d’élément avec la police dont le nom est identique à l’étiquette. La valeur par défaut de ce membre est `FALSE`.  
  
##  <a name="a-nameselectfonta--cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>CMFCFontComboBox::SelectFont  
 Sélectionne la police qui correspond aux critères spécifiés dans la zone de liste déroulante de police.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDesc`  
 Pointe vers un objet de description de police.  
  
 [in] `lpszName`  
 Spécifie un nom de police.  
  
 [in] `nCharSet`  
 Spécifie un jeu de caractères. La valeur par défaut est DEFAULT_CHARSET. Pour plus d’informations, consultez la `lfCharSet` membre de la [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un élément dans la zone de liste déroulante de police correspond à l’objet de description de police spécifiée ou nom de la police et de charset ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour sélectionner et faites défiler jusqu'à l’élément dans la zone de liste déroulante de police qui correspond à la police spécifiée.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `SelectFont` méthode dans la `CMFCFontComboBox` classe. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#35;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="a-namesetupa--cmfcfontcomboboxsetup"></a><a name="setup"></a>CMFCFontComboBox::Setup  
 Initialise la liste des éléments dans la zone de liste déroulante de police.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nFontType`  
 Spécifie le type de police. La valeur par défaut est la combinaison d’opérations de bits (OR) de DEVICE_FONTTYPE, RASTER_FONTTYPE et TRUETYPE_FONTTYPE.  
  
 [in] `nCharSet`  
 Spécifie le jeu de caractères de police. La valeur par défaut est DEFAULT_CHARSET.  
  
 [in] `nPitchAndFamily`  
 Spécifie la hauteur de police et de la famille. La valeur par défaut est DEFAULT_PITCH.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la zone de liste déroulante police a été initialisée avec succès ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode initialise la zone de liste déroulante de police en énumérant les polices actuellement installées qui correspondent aux paramètres spécifiés et en insérant les noms de police dans la zone de liste déroulante de police.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `Setup` méthode dans la `CMFCFontComboBox` classe. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#34;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls n °&36;](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox (classe)](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo (classe)](../../mfc/reference/cmfcfontinfo-class.md)

