---
title: Classe de CMFCColorPickerCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPickerCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPickerCtrl class
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
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
ms.openlocfilehash: 0a819d04535ba965e2c1a10f3761c442c9840538
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpickerctrl-class"></a>Classe de CMFCColorPickerCtrl
La `CMFCColorPickerCtrl` classe fournit les fonctionnalités pour un contrôle qui est utilisé pour sélectionner des couleurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Construit un objet `CMFCColorPickerCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Récupère la couleur que l’utilisateur sélectionne.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Récupère les valeurs de teinte, de luminance et de saturation de la couleur que l’utilisateur sélectionne.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Récupère le composant de teinte de la couleur que l’utilisateur sélectionne.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Récupère le composant de luminance de la couleur que l’utilisateur sélectionne.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Récupère le composant de saturation de la couleur que l’utilisateur sélectionne.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Définit la couleur actuelle à la couleur définie par les composants de couleur RVB spécifiés ou hexagone de la cellule spécifiée.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Définit la couleur actuelle à la valeur de couleur RVB spécifiée.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Définit la couleur actuelle à la valeur de couleur TSL spécifiée.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Modifie le composant de teinte de la couleur actuellement sélectionnée.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Modifie le composant de luminance de la couleur actuellement sélectionnée.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Définit la largeur de la barre de luminance dans le contrôle de sélecteur de couleurs.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Définit la couleur initiale sélectionnée.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Définit la palette de couleurs.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Modifie le composant de saturation de la couleur actuellement sélectionnée.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Définit le type de contrôle de sélecteur de couleurs à afficher.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Appelé par l’infrastructure avant un curseur qui pointe vers la couleur sélectionnée s’affiche.|  
  
## <a name="remarks"></a>Remarques  
 Couleurs standard sont sélectionnées à partir d’une palette de couleurs hexagonal et couleurs personnalisées sont sélectionnés à partir d’une barre de luminance lorsque les couleurs sont spécifiées à l’aide de la notation rouge/vert/bleu ou teinte/satuaration/luminance notation.  
  
 L’illustration suivante représente plusieurs `CMFCColorPickerCtrl` objets.  
  
 ![Boîte de dialogue CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 Le `CMFCColorPickerCtrl` prend en charge deux paires de styles. Les styles HEX et HEX_GREYSCALE sont appropriés pour la sélection de couleurs standard. Les styles de sélecteur et LUMINANCE sont appropriés pour la sélection d’une couleur personnalisée.  
  
 Procédez comme suit pour incorporer la `CMFCColorPickerCtrl` contrôle dans votre boîte de dialogue :  
  
1.  Si vous utilisez la **ClassWizard**, insérer un nouveau contrôle de bouton dans votre modèle de boîte de dialogue (car le `CMFCColorPickerCtrl` classe est héritée de la `CButton` classe).  
  
2.  Insérer une variable de membre qui est associée avec le nouveau contrôle de bouton dans votre classe de boîte de dialogue. Puis modifiez le type de variable à partir de `CButton` à `CMFCColorPickerCtrl`.  
  
3.  Insérer le `WM_INITDIALOG` Gestionnaire de messages pour la classe de boîte de dialogue. Dans le gestionnaire, définissez le type, palette et couleur sélectionnée initiale de la `CMFCColorPickerCtrl` contrôle.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer un `CMFCColorPickerCtrl` à l’aide de différentes méthodes dans la `CMFCColorPickerCtrl` classe. L’exemple montre comment définir le type du contrôle de sélecteur et comment définir sa couleur, la teinte, la luminance et la saturation. L’exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls n °&4;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls n °&5;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcolorpickerctrl.h  
  
##  <a name="a-namecmfccolorpickerctrla--cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Construit un objet `CMFCColorPickerCtrl`.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedrawcursora--cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor  
 Appelé par l’infrastructure avant un curseur qui pointe vers la couleur sélectionnée s’affiche.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Spécifie une zone rectangulaire autour de la couleur sélectionnée.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode lorsque vous devez modifier la forme du curseur qui pointe vers la couleur sélectionnée.  
  
##  <a name="a-namegetcolora--cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>CMFCColorPickerCtrl::GetColor  
 Récupère la couleur que l’utilisateur sélectionne.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur RVB de la couleur sélectionnée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegethlsa--cmfccolorpickerctrlgethls"></a><a name="gethls"></a>CMFCColorPickerCtrl::GetHLS  
 Récupère les valeurs de teinte, de luminance et de saturation de la couleur que l’utilisateur sélectionne.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `hue`  
 Pointeur vers une variable de type double qui reçoit des informations de teinte.  
  
 [out] `luminance`  
 Pointeur vers une variable de type double qui reçoit des informations de luminance.  
  
 [out] `saturation`  
 Pointeur vers une variable de type double qui reçoit des informations de saturation.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegethuea--cmfccolorpickerctrlgethue"></a><a name="gethue"></a>CMFCColorPickerCtrl::GetHue  
 Récupère le composant de teinte de la couleur que l’utilisateur sélectionne.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le composant de teinte de la couleur sélectionnée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetluminancea--cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance  
 Récupère le composant de luminance de la couleur que l’utilisateur sélectionne.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le composant de luminance de la couleur sélectionnée.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetsaturationa--cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation  
 Récupère la valeur de saturation de la couleur que l’utilisateur sélectionne.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le composant de saturation de la couleur sélectionnée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameselectcellhexagona--cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon  
 Définit la couleur actuelle à la couleur définie par les composants de couleur RVB spécifiés ou hexagone de la cellule spécifiée.  
  
```  
void SelectCellHexagon(
    BYTE R,  
    BYTE G,  
    BYTE B);

 
BOOL SelectCellHexagon(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `R`  
 Le composant de couleur rouge.  
  
 [in] `G`  
 Le composant de couleur verte.  
  
 [in] `B`  
 Le composant de couleur bleu.  
  
 [in] `x`  
 Coordonnée x du curseur, qui pointe vers un hexagone de cellule.  
  
 [in] `y`  
 Coordonnée y du curseur, qui pointe vers un hexagone de cellule.  
  
### <a name="return-value"></a>Valeur de retour  
 La deuxième surcharge de cette méthode retourne toujours `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 La première surcharge de cette méthode définit la couleur qui correspond au contrôle de sélection de couleur couleur actuel spécifiés composants de couleur rouge, vert et bleu.  
  
 La deuxième surcharge de cette méthode définit la couleur actuelle de la couleur de l’Hexagone cellule vers laquelle pointe par l’emplacement du curseur spécifié.  
  
##  <a name="a-namesetcolora--cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>CMFCColorPickerCtrl::SetColor  
 Définit la couleur actuelle à la valeur de couleur RVB spécifiée.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `Color`  
 Une valeur de couleur RVB.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesethlsa--cmfccolorpickerctrlsethls"></a><a name="sethls"></a>CMFCColorPickerCtrl::SetHLS  
 Définit la couleur actuelle à la valeur de couleur TSL spécifiée.  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hue`  
 Une valeur de teinte.  
  
 [in] `luminance`  
 Une valeur de luminance.  
  
 [in] `saturation`  
 Une valeur de saturation.  
  
 [in] `bInvalidate`  
 `TRUE`Pour forcer la fenêtre Mettre à jour immédiatement la nouvelle couleur ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesethuea--cmfccolorpickerctrlsethue"></a><a name="sethue"></a>CMFCColorPickerCtrl::SetHue  
 Modifie la teinte de la couleur actuellement sélectionnée.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `Hue`  
 Une valeur de teinte.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetluminancea--cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance  
 Modifie la luminance de la couleur actuellement sélectionnée.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `Luminance`  
 Une valeur de luminance.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetluminancebarwidtha--cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Définit la largeur de la barre de luminance dans le contrôle de sélecteur de couleurs.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `w`  
 La largeur de la barre de luminance en pixels.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour redimensionner la barre de luminance, qui se trouve sur le **personnalisé** onglet du contrôle de sélecteur de couleur. Le `w` paramètre spécifie la nouvelle largeur de la barre de luminance. La valeur de la largeur est ignorée si elle dépasse trois quarts de la largeur de la zone cliente.  
  
##  <a name="a-namesetoriginalcolora--cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor  
 Définit la couleur initiale sélectionnée.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ref`  
 Une valeur de couleur RVB.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode lorsque le contrôle de sélecteur de couleurs est initialisé.  
  
##  <a name="a-namesetpalettea--cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette  
 Définit la palette de couleurs.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPalette`  
 Pointeur vers une palette de couleurs.  
  
### <a name="remarks"></a>Remarques  
 La palette de couleurs définit le tableau de couleurs qui s’affiche dans le contrôle de sélecteur de couleurs.  
  
##  <a name="a-namesetsaturationa--cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation  
 Modifie la saturation de la couleur actuellement sélectionnée.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `Saturation`  
 Une valeur de saturation.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesettypea--cmfccolorpickerctrlsettype"></a><a name="settype"></a>CMFCColorPickerCtrl::SetType  
 Définit le type de contrôle de sélecteur de couleurs à afficher.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `colorType`  
 Un type de contrôle de sélecteur de couleurs.  
  
 Les types définis par le `CMFCColorPickerCtrl::COLORTYPE` (énumération). Les types possibles sont `LUMINANCE`, `PICKER`, `HEX` et `HEX_GREYSCALE`. Le type par défaut est `PICKER`.  
  
### <a name="remarks"></a>Remarques  
 Pour spécifier un type de contrôle de sélecteur de couleurs, appelez cette méthode avant la création du contrôle Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog (classe)](../../mfc/reference/cmfccolordialog-class.md)

