---
title: Classe de CMFCRibbonFontComboBox | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox class
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
caps.latest.revision: 24
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9bf968571f9a1bcdbce57c3559b3d70e7692ebe0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="cmfcribbonfontcombobox-class"></a>Classe de CMFCRibbonFontComboBox
Implémente une zone de liste déroulante contenant une liste de polices. Vous placez la zone de liste déroulante sur un panneau de ruban.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Destructeur.|  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Construit et initialise un objet `CMFCRibbonFontComboBox`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Remplit la zone de liste modifiable Police du ruban avec des polices du type, du jeu de caractères, du pas et de la famille spécifiés.|  
|`CMFCRibbonFontComboBox::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Retourne le jeu de caractères spécifié.|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Retourne les types de police à afficher dans la zone de liste modifiable. Les options valides sont DEVICE_FONTTYPE, RASTER_FONTTYPE et TRUETYPE_FONTTYPE ou toute autre combinaison au niveau du bit de ces options.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Retourne le pas et la famille des polices affichées dans la zone de liste modifiable.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Utilisé par l’infrastructure pour obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet qui est associé à ce type de classe.|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Remplit la zone de liste modifiable Police du ruban avec des polices du type, du jeu de caractères, du pas et de la famille spécifiés précédemment.|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Sélectionne la police spécifiée dans la zone de liste modifiable.|  
  
## <a name="remarks"></a>Remarques  
 Après avoir créé un `CMFCRibbonFontComboBox` d’objet, ajoutez-le à un panneau de ruban en appelant [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonComboBox.h  
  
##  <a name="buildfonts"></a>CMFCRibbonFontComboBox::BuildFonts  
 Remplit la zone de liste déroulante du ruban avec des polices.  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nFontType`  
 Spécifie le type de police des polices à ajouter.  
  
 [in] `nCharSet`  
 Spécifie le jeu de caractères des polices à ajouter.  
  
 [in] `nPitchAndFamily`  
 Spécifie la hauteur et la famille de polices à ajouter.  
  
##  <a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 Construit et initialise un [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) objet.  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 L’ID de commande de la commande qui s’exécute lorsque l’utilisateur sélectionne un élément dans la zone de liste déroulante.  
  
 [in] `nFontType`  
 Spécifie les types de police à afficher dans la zone de liste déroulante. Les options valides sont **DEVICE_FONTTYPE**, **RASTER_FONTTYPE**, et **TRUETYPE_FONTTYPE**, ou toute autre combinaison au niveau du bit.  
  
 [in] `nCharSet`  
 Filtre les polices dans la zone de liste déroulante à ceux qui appartiennent au jeu de caractères spécifié...  
  
 [in] `nPitchAndFamily`  
 Spécifie la hauteur et la famille de polices qui s’affichent dans la zone de liste déroulante.  
  
 [in] `nWidth`  
 Spécifie la largeur, en pixels, de la zone de liste déroulante.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur les éventuelles `nFontType` les valeurs de paramètre, consultez [EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) dans la documentation du Kit de développement logiciel Windows.  
  
 Pour plus d’informations sur les jeux de caractères valide qui peut être assigné à `nCharSet`et les valeurs valides qui peuvent être affectés à `nPitchAndFamily`, consultez [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) dans la documentation du Kit de développement logiciel Windows.  
  
##  <a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iIndex`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildFonts  
 Remplit la zone de liste déroulante du ruban avec des polices, d’un type de police spécifié précédemment, le jeu de caractères et la tonalité et la famille.  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez spécifier le type de police, le jeu de caractères, et pas et la famille de polices à inclure dans la liste déroulante de police du ruban zone le [constructeur](#cmfcribbonfontcombobox) à cette classe, ou en appelant [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="setfont"></a>CMFCRibbonFontComboBox::SetFont  
 Sélectionne la police spécifiée dans la zone de liste modifiable.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Spécifie le nom de la police à sélectionner.  
  
 `nCharSet`  
 Spécifie le jeu de caractères de la police sélectionnée.  
  
 `bExact`  
 `TRUE`Pour spécifier que le jeu de caractères doit correspondre à lors de la sélection d’une police ; `FALSE` pour spécifier que le jeu de caractères peut être ignoré lors de la sélection d’une police.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la police spécifiée est introuvable et est sélectionnée ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharSet  
 Retourne le jeu de caractères spécifié.  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Jeu de caractères (voir LOGFONT dans la documentation du Kit de développement).  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType  
 Retourne les types de police à afficher dans la zone de liste modifiable. Les options valides sont DEVICE_FONTTYPE, RASTER_FONTTYPE et TRUETYPE_FONTTYPE ou toute autre combinaison au niveau du bit de ces options.  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Types de polices (voir EnumFontFamProc dans la documentation du Kit de développement).  
  
### <a name="remarks"></a>Notes  
  
##  <a name="getpitchandfamily"></a>CMFCRibbonFontComboBox::GetPitchAndFamily  
 Retourne le pas et la famille des polices affichées dans la zone de liste modifiable.  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Espacement et la famille (voir LOGFONT dans la documentation du Kit de développement).  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox, classe](../../mfc/reference/cmfcribboncombobox-class.md)

