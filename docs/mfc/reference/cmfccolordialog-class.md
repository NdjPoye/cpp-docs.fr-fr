---
title: Classe de CMFCColorDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog::m_CurrentColor data member
- CMFCColorDialog::m_pPropSheet data member
- CMFCColorDialog::m_btnColorSelect data member
- CMFCColorDialog class
- CMFCColorDialog::m_wndColors data member
- CMFCColorDialog::m_bIsMyPalette data member
- CMFCColorDialog::m_pColourSheetTwo data member
- CMFCColorDialog::m_NewColor data member
- CMFCColorDialog::m_pPalette data member
- CMFCColorDialog::m_wndStaticPlaceHolder data member
- CMFCColorDialog::m_pColourSheetOne data member
- CMFCColorDialog::m_hcurPicker data member
- CMFCColorDialog::PreTranslateMessage method
- CMFCColorDialog::m_bPickerMode data member
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
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
ms.openlocfilehash: ac621157e0fcb5bcabef2ae8f367a1b141b4ace0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog (classe)
La `CMFCColorDialog` classe représente une boîte de dialogue de sélection de couleur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Construit un objet `CMFCColorDialog`.|  
|`CMFCColorDialog::~CMFCColorDialog`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Retourne la couleur sélectionnée en cours.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Retourne les palette de couleur.|  
|`CMFCColorDialog::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. Pour la syntaxe et plus d’informations, consultez [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Substitue `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Dérive une palette de la palette système.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Définit la couleur sélectionnée en cours.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Définit la couleur plus équivalente à la valeur RVB spécifiée.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Sélectionne une valeur RVB de la première page de propriété.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Sélectionne une valeur RVB de la deuxième page de propriétés.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`Si la boîte de dialogue de sélection de couleur utilise sa propre palette de couleurs, ou `FALSE` si la boîte de dialogue utilise une palette qui est spécifiée dans le `CMFCColorDialog` constructeur.|  
|`m_bPickerMode`|`TRUE`Bien que l’utilisateur sélectionne une couleur à partir de la boîte de dialogue de sélection ; dans le cas contraire, `FALSE`.|  
|`m_btnColorSelect`|Le bouton de couleur sélectionnée par l’utilisateur.|  
|`m_CurrentColor`|La couleur actuellement sélectionnée.|  
|`m_hcurPicker`|Le curseur permet de choisir une couleur.|  
|`m_NewColor`|Couleur sélectionnée potentiel, qui peut être définitivement sélectionnée ou restauration de la couleur d’origine.|  
|`m_pColourSheetOne`|Pointeur vers la première page de propriété de la feuille de propriétés de sélection de couleur.|  
|`m_pColourSheetTwo`|Pointeur vers la deuxième page de propriétés de la feuille de propriétés de sélection de couleur.|  
|`m_pPalette`|La palette logique en cours.|  
|`m_pPropSheet`|Pointeur vers la feuille de propriétés de la boîte de dialogue de sélection de couleur.|  
|`m_wndColors`|Un objet de contrôle de sélecteur de couleurs.|  
|`m_wndStaticPlaceHolder`|Un contrôle statique est un espace réservé pour la feuille de propriétés de sélecteur de couleurs.|  
  
## <a name="remarks"></a>Remarques  
 La boîte de dialogue de sélection de couleur s’affiche comme une feuille de propriétés avec deux pages. Sur la première page, vous sélectionnez une couleur standard à partir de la palette système. sur la deuxième page, vous sélectionnez une couleur personnalisée.  
  
 Vous pouvez construire un `CMFCColorDialog` de l’objet sur la pile, puis appelez `DoModal`, en passant la couleur initiale en tant que paramètre à la `CMFCColorDialog` constructeur. La boîte de dialogue de sélection de couleur, puis crée plusieurs [CMFCColorPickerCtrl classe](../../mfc/reference/cmfccolorpickerctrl-class.md) objets pour traiter chaque palette de couleurs.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer une boîte de dialogue couleur à l’aide de différentes méthodes dans la `CMFCColorDialog` classe. L’exemple montre comment définir les actuels et les nouvelles couleurs de la boîte de dialogue et comment définir les composants rouges, verts et bleus de la couleur sélectionnée sur les pages de deux propriétés de la boîte de dialogue couleur. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls n °&3;](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog  
 Construit un objet `CMFCColorDialog`.  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `clrInit`  
 La sélection de couleur par défaut. Si aucune valeur n’est spécifiée, la valeur par défaut est RGB(0,0,0) (noir).  
  
 [in] `dwFlags`  
 (Réservé).  
  
 [in] `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de la boîte de dialogue.  
  
 [in] `hPal`  
 Handle vers une palette de couleurs.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getcolor"></a>CMFCColorDialog::GetColor  
 Récupère la couleur de l’utilisateur sélectionne dans la boîte de dialogue couleur.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) valeur qui contient les informations RVB de la couleur sélectionnée dans la boîte de dialogue couleur.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction après avoir appelé la `DoModal` méthode.  
  
##  <a name="getpalette"></a>CMFCColorDialog::GetPalette  
 Récupère la palette de couleurs qui est disponible dans la boîte de dialogue couleur actuelle.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `CPalette` objet qui a été spécifié dans le `CMFCColorDialog` constructeur.  
  
### <a name="remarks"></a>Notes  
 La palette de couleurs spécifie les couleurs de l’utilisateur peut choisir.  
  
##  <a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette  
 Dérive une palette de la palette système.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor  
 Définit la couleur de la boîte de dialogue actuelle.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rgb`  
 Une valeur de couleur RVB  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setnewcolor"></a>CMFCColorDialog::SetNewColor  
 Définit la couleur actuelle à la couleur de la palette actuelle est la plus proche.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `rgb`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) qui spécifie une couleur RVB.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="setpageone"></a>CMFCColorDialog::SetPageOne  
 Spécifie explicitement les composants rouges, verts et bleus de la couleur sélectionnée sur la première page de propriété de boîte de dialogue couleur.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `R`  
 Spécifie la composante rouge de la valeur RVB.  
  
 [in] `G`  
 Spécifie la composante verte de la valeur RVB.  
  
 [in] `B`  
 Spécifie la composante bleue de la valeur RVB.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo  
 Spécifie explicitement les composants rouges, verts et bleus de la couleur sélectionnée sur la deuxième page de propriété de boîte de dialogue couleur.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `R`  
 Spécifie un composant rouge de la valeur RVB  
  
 [in] `G`  
 Spécifie un composant vert d’une valeur RVB  
  
 [in] `B`  
 Spécifie un composant d’une valeur RVB bleu  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

