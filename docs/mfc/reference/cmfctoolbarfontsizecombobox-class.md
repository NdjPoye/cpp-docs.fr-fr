---
title: Classe de CMFCToolBarFontSizeComboBox | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox class
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
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
ms.openlocfilehash: 9dddb563617a708bdc8b2193fa5ee8bd10321828
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox (classe)
Un bouton de barre d’outils qui contient un contrôle de zone de liste déroulante qui permet à l’utilisateur de sélectionner une taille de police.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Construit un objet `CMFCToolBarFontSizeComboBox`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Retourne la taille de police sélectionnée en twips.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Remplit la zone de liste modifiable avec toutes les tailles de police prise en charge d’une police spécifiée.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Définit la taille de police en twips.|  
  
## <a name="remarks"></a>Remarques  
 Vous pouvez utiliser un `CMFCToolBarFontSizeComboBox` de l’objet avec un [CMFCToolBarFontComboBox classe](../../mfc/reference/cmfctoolbarfontcombobox-class.md) objet pour permettre à un utilisateur de sélectionner une police et une taille de police.  
  
 Vous pouvez ajouter un bouton de zone de liste déroulante Taille police à une barre d’outils comme vous ajoutez un bouton de zone de liste déroulante de police. Pour plus d’informations, consultez [CMFCToolBarFontComboBox classe](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Lorsque l’utilisateur sélectionne une nouvelle police dans un `CMFCToolBarFontComboBox` de l’objet, vous pouvez remplir la zone de liste déroulante de taille de police avec les tailles prises en charge pour cette police en utilisant la [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) (méthode).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser différentes méthodes dans le `CMFCToolBarFontSizeComboBox` classe pour configurer un `CMFCToolBarFontSizeComboBox` objet. L’exemple montre comment récupérer la taille de police, en twips, à partir de la zone de texte, remplir la zone de liste déroulante de taille de police avec toutes les tailles valides de la police donnée et spécifier la taille de police en twips. Cet extrait de code fait partie de la [exemple du bloc-notes](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad n °&8;](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 Construit un objet `CMFCToolBarFontSizeComboBox`.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize  
 Récupère la taille de police, en twips, à partir de la zone de texte d’une zone de liste déroulante de taille de police.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est positive, il est la taille de police en twips. Il est -1 si la zone de texte de la zone de liste déroulante est vide. Il est -2 si une erreur se produit.  
  
##  <a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 Remplit une zone de liste déroulante de taille de police avec toutes les tailles valides de la police donnée.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>Paramètres  
 `[in] strFontName`  
 Spécifie un nom de police.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction lorsque vous souhaitez synchroniser entre la sélection dans une zone de liste déroulante de police et une zone de liste déroulante taille de police, comme un [CMFCToolBarFontComboBox classe](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize  
 Arrondit spécifié une taille (en twips) de la taille la plus proche des points, puis définit la taille sélectionnée dans la zone de liste déroulante valeur.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nSize`  
 Spécifie la taille de police (en twips) pour définir.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez récupérer ultérieurement la taille de police valide précédente en appelant le [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton (classe)](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton (classe)](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo (classe)](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Procédure pas à pas : Placement de contrôles dans les barres d’outils](../../mfc/walkthrough-putting-controls-on-toolbars.md)




