---
title: Classe de CMFCPropertySheet | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertySheet
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertySheet::PreTranslateMessage method
- CMFCPropertySheet::OnInitDialog method
- CMFCPropertySheet class
ms.assetid: 01d93573-9698-440f-a6a4-5bebbee879dc
caps.latest.revision: 35
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
ms.openlocfilehash: a157a0afa4542bc023ba4d7149e78a71bbd56e74
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertysheet-class"></a>Classe de CMFCPropertySheet
La classe `CMFCPropertySheet` prend en charge une feuille de propriétés où chaque page de propriétés est représentée par un onglet de page, un bouton de barre d'outils, un nœud de contrôle d'arborescence ou un élément de liste.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCPropertySheet : public CPropertySheet  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPropertySheet::CMFCPropertySheet](#cmfcpropertysheet)|Construit un objet `CMFCPropertySheet`.|  
|`CMFCPropertySheet::~CMFCPropertySheet`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCPropertySheet::AddPage](#addpage)|Ajoute une page à la feuille de propriétés.|  
|[CMFCPropertySheet::AddPageToTree](#addpagetotree)|Ajoute une nouvelle page de propriétés au contrôle d’arborescence.|  
|[CMFCPropertySheet::AddTreeCategory](#addtreecategory)|Ajoute un nouveau nœud au contrôle d’arborescence.|  
|[CMFCPropertySheet::EnablePageHeader](#enablepageheader)|Réserve de l'espace en haut de chaque page pour dessiner un en-tête personnalisé.|  
|[CMFCPropertySheet::GetHeaderHeight](#getheaderheight)|Récupère la hauteur de l'en-tête actuel.|  
|[CMFCPropertySheet::GetLook](#getlook)|Récupère une valeur d'énumération qui spécifie l'apparence de la feuille de propriétés actuelle.|  
|[CMFCPropertySheet::GetNavBarWidth](#getnavbarwidth)|Réessaie la largeur de la barre de navigation en pixels.|  
|[CMFCPropertySheet::GetTab](#gettab)|Récupère l'objet de contrôle d'onglet interne qui prend en charge le contrôle de feuille de propriétés actuel.|  
|`CMFCPropertySheet::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol)|Initialise l'apparence du contrôle de feuille de propriétés actuel.|  
|[CMFCPropertySheet::OnActivatePage](#onactivatepage)|Appelé par l'infrastructure quand une page de propriétés est activée.|  
|[CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader)|Appelé par l'infrastructure pour dessiner un en-tête de page de propriétés personnalisé.|  
|`CMFCPropertySheet::OnInitDialog`|Gère la [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) message. (Substitue [CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|  
|[CMFCPropertySheet::OnRemoveTreePage](#onremovetreepage)|Appelé par l’infrastructure pour supprimer une page de propriétés d’un contrôle d’arborescence.|  
|`CMFCPropertySheet::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue `CPropertySheet::PreTranslateMessage`.)|  
|[CMFCPropertySheet::RemoveCategory](#removecategory)|Supprime un nœud du contrôle d’arborescence.|  
|[CMFCPropertySheet::RemovePage](#removepage)|Supprime une page de propriétés de la feuille de propriétés.|  
|[CMFCPropertySheet::SetIconsList](#seticonslist)|Spécifie la liste des images utilisées dans le contrôle de navigation du volet Outlook.|  
|[CMFCPropertySheet::SetLook](#setlook)|Spécifie l'apparence de la feuille de propriétés.|  
  
## <a name="remarks"></a>Notes  
 La classe `CMFCPropertySheet` représente les feuilles de propriétés, aussi appelées boîtes de dialogue à onglets. La classe `CMFCPropertySheet` peut afficher une page de propriétés de diverses manières.  
  
 Pour utiliser la classe `CMFCPropertySheet` dans votre application, procédez comme suit :  
  
1.  Faites dériver une classe de la classe `CMFCPropertySheet` et nommez-la, par exemple, CMyPropertySheet.  
  
2.  Construire un [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md) objet pour chaque page de propriétés.  
  
3.  Appelez le [CMFCPropertySheet::SetLook](#setlook) méthode dans le constructeur CMyPropertySheet. Un paramètre de cette méthode permet de spécifier sous quelle forme les pages de propriétés seront affichées : onglets le long de la bordure supérieure ou gauche de la feuille de propriétés ; onglets dans le style d’une feuille de propriétés Microsoft OneNote ; boutons sur un contrôle de barre d’outils Microsoft Outlook ; nœuds sur un contrôle d’arborescence ; ou liste d’éléments sur le côté gauche de la feuille de propriétés.  
  
4.  Si vous créez une feuille de propriétés dans le style d’une barre d’outils de Microsoft Outlook, appelez le [CMFCPropertySheet::SetIconsList](#seticonslist) pour associer une liste d’images avec les pages de propriétés.  
  
5.  Appelez le [CMFCPropertySheet::AddPage](#addpage) méthode pour chaque page de propriétés.  
  
6.  Créez un contrôle `CMFCPropertySheet` et appelez sa méthode `DoModal`.  
  
## <a name="illustrations"></a>Illustrations  
 L'illustration suivante représente une feuille de propriétés dont le style est celui d'une barre d'outils Microsoft Outlook incorporée. La barre d'outils Outlook s'affiche sur le côté gauche de la feuille de propriétés.  
  
 ![Des couleurs CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_color.png "cmfcpropertysheet_color")  
  
 L’illustration suivante représente une feuille de propriétés contenant un [CMFCPropertyGridCtrl classe](../../mfc/reference/cmfcpropertygridctrl-class.md) objet. Cet objet est une feuille de propriétés dont le style est celui d'une feuille de propriétés de contrôles communs standard.  
  
 ![Liste et propriété CMFCPropertySheet](../../mfc/reference/media/cmfcpropertysheet_list.png "cmfcpropertysheet_list")  
  
 L’illustration suivante représente une feuille de propriétés dont le style est celui d’un contrôle d’arborescence.  
  
 ![Arborescence de propriétés](../../mfc/reference/media/proptree.png "proptree")  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxpropertysheet.h  
  
##  <a name="a-nameaddpagea--cmfcpropertysheetaddpage"></a><a name="addpage"></a>CMFCPropertySheet::AddPage  
 Ajoute une page à la feuille de propriétés.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPage`  
 Pointeur vers un objet page. Ce paramètre ne peut pas être `NULL`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode ajoute la page de propriétés spécifié comme l’onglet à l’extrême droite de la feuille de propriétés. Par conséquent, utilisez cette méthode pour ajouter des pages dans l’ordre de gauche à droite.  
  
 Si la feuille de propriétés est dans le style de Microsoft Outlook, l’infrastructure affiche une liste des boutons de navigation à gauche de la feuille de propriétés. Une fois que cette méthode ajoute une page de propriétés, il ajoute un bouton correspondant à la liste. Pour afficher une page de propriétés, cliquez sur le bouton correspondant. Pour plus d’informations sur les styles de feuilles de propriétés, consultez [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-nameaddpagetotreea--cmfcpropertysheetaddpagetotree"></a><a name="addpagetotree"></a>CMFCPropertySheet::AddPageToTree  
 Ajoute une nouvelle page de propriétés au contrôle d’arborescence.  
  
```  
void AddPageToTree(
    CMFCPropertySheetCategoryInfo* pCategory,  
    CMFCPropertyPage* pPage,  
    int nIconNum=-1,  
    int nSelIconNum=-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pCategory`  
 Pointeur vers un nœud d’arborescence parent, ou `NULL` à associer la page spécifiée avec le nœud de niveau supérieur. Appelez le [CMFCPropertySheet::AddTreeCategory](#addtreecategory) méthode pour obtenir ce pointeur.  
  
 [in] `pPage`  
 Pointeur vers un objet de page de propriétés.  
  
 [in] `nIconNum`  
 Index de base zéro d’une icône, ou -1 si aucune icône n’est utilisé. Lorsque la page n’est pas sélectionnée, l’icône s’affiche en regard de la page de propriétés du contrôle arborescence. La valeur par défaut est -1.  
  
 [in] `nSelIconNum`  
 Index de base zéro d’une icône, ou -1 si aucune icône n’est utilisé. Lorsque la page est sélectionnée, l’icône s’affiche en regard de la page de propriétés du contrôle arborescence. La valeur par défaut est -1.  
  
### <a name="remarks"></a>Notes  
 Cette méthode ajoute une page de propriétés comme une feuille d’un contrôle d’arborescence. Pour ajouter une page de propriétés, créez un `CMFCPropertySheet` de l’objet, appelez le [CMFCPropertySheet::SetLook](#setlook) méthode avec la `look` paramètre défini sur `CMFCPropertySheet::PropSheetLook_Tree`, puis utilisez cette méthode pour ajouter la page de propriétés.  
  
##  <a name="a-nameaddtreecategorya--cmfcpropertysheetaddtreecategory"></a><a name="addtreecategory"></a>CMFCPropertySheet::AddTreeCategory  
 Ajoute un nouveau nœud au contrôle d’arborescence.  
  
```  
CMFCPropertySheetCategoryInfo* AddTreeCategory(
    LPCTSTR lpszLabel,  
    int nIconNum=-1,  
    int nSelectedIconNum=-1,  
    const CMFCPropertySheetCategoryInfo* pParentCategory=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszLabel`  
 Nom du nœud.  
  
 [in] `nIconNum`  
 Index de base zéro d’une icône, ou -1 si aucune icône n’est utilisé. Lorsque la page n’est pas sélectionnée, l’icône s’affiche en regard de la page de propriétés du contrôle arborescence. La valeur par défaut est -1.  
  
 [in] `nSelectedIconNum`  
 Index de base zéro d’une icône, ou -1 si aucune icône n’est utilisé. Lorsque la page est sélectionnée, l’icône s’affiche en regard de la page de propriétés du contrôle arborescence. La valeur par défaut est -1.  
  
 [in] `pParentCategory`  
 Pointeur vers un nœud d’arborescence parent, ou `NULL` à associer la page spécifiée avec le nœud de niveau supérieur. Définissez ce paramètre avec le [CMFCPropertySheet::AddTreeCategory](#addtreecategory) (méthode).  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le nouveau nœud dans le contrôle d’arborescence.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour ajouter un nouveau nœud, qui est également appelé une catégorie, au contrôle d’arborescence. Pour ajouter un nœud, créez un `CMFCPropertySheet` de l’objet, appelez le [CMFCPropertySheet::SetLook](#setlook) méthode avec la `look` paramètre défini sur `CMFCPropertySheet::PropSheetLook_Tree`, puis utilisez cette méthode pour ajouter le nœud.  
  
 Utilisez la valeur de retour de cette méthode dans les appels suivants à [CMFCPropertySheet::AddPageToTree](#addpagetotree) et [CMFCPropertySheet::AddTreeCategory](#addtreecategory).  
  
##  <a name="a-namecmfcpropertysheeta--cmfcpropertysheetcmfcpropertysheet"></a><a name="cmfcpropertysheet"></a>CMFCPropertySheet::CMFCPropertySheet  
 Construit un objet `CMFCPropertySheet`.  
  
```  
CMFCPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);

CMFCPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd=NULL,  
    UINT iSelectPage=0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszCaption`  
 Chaîne qui contient la légende de la feuille des propriétés. Ne peut pas être `NULL`.  
  
 [in] `nIDCaption`  
 Un ID de ressource qui contient la légende de la feuille des propriétés.  
  
 [in] `pParentWnd`  
 Pointeur vers la fenêtre parente de la feuille de propriétés, ou `NULL` si la fenêtre parente est la fenêtre principale de l’application. La valeur par défaut est `NULL`.  
  
 [in] `iSelectPage`  
 Index de base zéro de la page de propriété du haut. La valeur par défaut est 0.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez les paramètres pour le [CPropertySheet::CPropertySheet](../../mfc/reference/cpropertysheet-class.md#cpropertysheet) constructeur.  
  
##  <a name="a-nameenablepageheadera--cmfcpropertysheetenablepageheader"></a><a name="enablepageheader"></a>CMFCPropertySheet::EnablePageHeader  
 Réserve de l'espace en haut de chaque page pour dessiner un en-tête personnalisé.  
  
```  
void EnablePageHeader(int nHeaderHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nHeaderHeight`  
 La hauteur de l’en-tête, en pixels.  
  
### <a name="remarks"></a>Remarques  
 Pour utiliser la valeur de la `nHeaderHeight` paramètre pour dessiner un en-tête personnalisé, substituez la [CMFCPropertySheet::OnDrawPageHeader](#ondrawpageheader) (méthode).  
  
##  <a name="a-namegetheaderheighta--cmfcpropertysheetgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertySheet::GetHeaderHeight  
 Récupère la hauteur de l'en-tête actuel.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur de l’en-tête, en pixels.  
  
### <a name="remarks"></a>Notes  
 Appelez le [CMFCPropertySheet::EnablePageHeader](#enablepageheader) méthode avant d’appeler cette méthode.  
  
##  <a name="a-namegetlooka--cmfcpropertysheetgetlook"></a><a name="getlook"></a>CMFCPropertySheet::GetLook  
 Récupère une valeur d'énumération qui spécifie l'apparence de la feuille de propriétés actuelle.  
  
```  
PropSheetLook GetLook() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs d’énumération qui spécifie l’apparence de la feuille de propriétés. Pour obtenir la liste des valeurs possibles, consultez la table d’énumération dans la section Notes de [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-namegetnavbarwidtha--cmfcpropertysheetgetnavbarwidth"></a><a name="getnavbarwidth"></a>CMFCPropertySheet::GetNavBarWidth  
 Obtient la largeur de la barre de navigation.  
  
```  
int GetNavBarWidth() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Largeur de la barre de navigation en pixels.  
  
##  <a name="a-namegettaba--cmfcpropertysheetgettab"></a><a name="gettab"></a>CMFCPropertySheet::GetTab  
 Récupère l'objet de contrôle d'onglet interne qui prend en charge le contrôle de feuille de propriétés actuel.  
  
```  
CMFCTabCtrl& GetTab() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un objet de contrôle onglet interne.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez définir une feuille de propriétés afin qu’il apparaisse dans différents styles, telle qu’un contrôle d’arborescence, une liste des boutons de navigation, ou un ensemble de pages à onglets.  
  
 Avant d’appeler cette méthode, appelez la [CMFCPropertySheet::SetLook](#setlook) pour définir l’apparence du contrôle de feuille de propriétés. Appelez ensuite la [CMFCPropertySheet::InitNavigationControl](#initnavigationcontrol) méthode pour initialiser l’objet de contrôle onglet interne. Utilisez cette méthode pour récupérer l’objet de contrôle onglet et ensuite utiliser cet objet pour travailler avec les onglets de la feuille de propriétés.  
  
 Si le contrôle de feuille de propriétés n’est pas défini pour s’affichent dans le style de Microsoft OneNote, cette méthode déclare en mode débogage.  
  
##  <a name="a-nameinitnavigationcontrola--cmfcpropertysheetinitnavigationcontrol"></a><a name="initnavigationcontrol"></a>CMFCPropertySheet::InitNavigationControl  
 Initialise l'apparence du contrôle de feuille de propriétés actuel.  
  
```  
virtual CWnd* InitNavigationControl();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre de contrôle de feuille de propriétés.  
  
### <a name="remarks"></a>Notes  
 Un contrôle de feuille de propriétés peut apparaître dans plusieurs formulaires, comme un ensemble de pages à onglets, un contrôle d’arborescence ou une liste de boutons de navigation. Utilisez le [CMFCPropertySheet::SetLook](#setlook) méthode pour spécifier l’apparence du contrôle de feuille de propriétés.  
  
##  <a name="a-nameonactivatepagea--cmfcpropertysheetonactivatepage"></a><a name="onactivatepage"></a>CMFCPropertySheet::OnActivatePage  
 Appelé par l'infrastructure quand une page de propriétés est activée.  
  
```  
virtual void OnActivatePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPage`  
 Pointeur vers un objet de page de propriété qui représente la page de propriété enabled.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, cette méthode garantit que la page de propriété enabled est affichée. Si le style de la feuille de propriété en cours contient un volet de Microsoft Outlook, cette méthode définit le bouton Outlook correspondant à l’état activé.  
  
##  <a name="a-nameondrawpageheadera--cmfcpropertysheetondrawpageheader"></a><a name="ondrawpageheader"></a>CMFCPropertySheet::OnDrawPageHeader  
 Appelé par l’infrastructure pour dessiner l’en-tête de page de propriétés personnalisée.  
  
```  
virtual void OnDrawPageHeader(
    CDC* pDC,  
    int nPage,  
    CRect rectHeader);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `nPage`  
 Le numéro de page de propriété de base zéro.  
  
 [in] `rectHeader`  
 Un rectangle englobant qui spécifie où dessiner l’en-tête.  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode ne fait rien. Si vous substituez cette méthode, appelez la [CMFCPropertySheet::EnablePageHeader](#enablepageheader) avant le framework appelle cette méthode.  
  
##  <a name="a-nameonremovetreepagea--cmfcpropertysheetonremovetreepage"></a><a name="onremovetreepage"></a>CMFCPropertySheet::OnRemoveTreePage  
 Appelé par l’infrastructure pour supprimer une page de propriétés d’un contrôle d’arborescence.  
  
```  
virtual BOOL OnRemoveTreePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPage`  
 Pointeur vers un objet de page de propriété qui représente la page de propriétés à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire, `FALSE`.  
  
##  <a name="a-nameremovecategorya--cmfcpropertysheetremovecategory"></a><a name="removecategory"></a>CMFCPropertySheet::RemoveCategory  
 Supprime un nœud du contrôle d’arborescence.  
  
```  
void RemoveCategory(CMFCPropertySheetCategoryInfo* pCategory);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pCategory`  
 Pointeur vers une catégorie (nœud) à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour supprimer un nœud, qui est également désigné comme une catégorie, à partir d’un contrôle d’arborescence. Utilisez le [CMFCPropertySheet::AddTreeCategory](#addtreecategory) pour ajouter un nœud à un contrôle d’arborescence.  
  
##  <a name="a-nameremovepagea--cmfcpropertysheetremovepage"></a><a name="removepage"></a>CMFCPropertySheet::RemovePage  
 Supprime une page de propriétés de la feuille de propriétés.  
  
```  
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pPage`  
 Pointeur vers un objet de page de propriétés qui représente la page de propriétés à supprimer. Ne peut pas être `NULL`.  
  
 [in] `nPage`  
 Index de base zéro de la page à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode supprime la page de propriété spécifiée et détruit la fenêtre associée. La page de propriétés de l’objet qui le `pPage` paramètre spécifie n’est pas détruit tant que le [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) fenêtre est fermée.  
  
##  <a name="a-nameseticonslista--cmfcpropertysheetseticonslist"></a><a name="seticonslist"></a>CMFCPropertySheet::SetIconsList  
 Spécifie la liste des images utilisées dans le contrôle de navigation du volet Outlook.  
  
```  
BOOL SetIconsList(
    UINT uiImageListResID,  
    int cx,  
    COLORREF clrTransparent=RGB(255, 0, 255));
void SetIconsList(HIMAGELIST hIcons);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiImageListResID`  
 L’ID de ressource d’une liste d’images.  
  
 [in] `cx`  
 La largeur, en pixels, des icônes dans la liste d’images.  
  
 [in] `clrTransparent`  
 La couleur de l’image transparente. Les parties de l’image qui sont de cette couleur est transparents. La valeur par défaut est la couleur magenta, RGB(255,0,255).  
  
 [in] `hIcons`  
 Handle vers une liste d’images existant.  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première méthode de surcharge syntaxe, `TRUE` si cette méthode réussit ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Si la feuille de propriétés est dans le style de Microsoft Outlook, l’infrastructure affiche une liste des boutons de navigation, appelée le contrôle de volet Outlook, à gauche de la feuille de propriétés. Utilisez cette méthode pour définir la liste d’images à utiliser par le contrôle de volet d’Outlook.  
  
 Pour plus d’informations sur les méthodes qui prennent en charge cette méthode, consultez [CImageList::Create](../../mfc/reference/cimagelist-class.md#create) et [CImageList::Add](../../mfc/reference/cimagelist-class.md#add). Pour plus d’informations sur la façon de définir le style d’une feuille de propriétés, consultez [CMFCPropertySheet::SetLook](#setlook).  
  
##  <a name="a-namesetlooka--cmfcpropertysheetsetlook"></a><a name="setlook"></a>CMFCPropertySheet::SetLook  
 Spécifie l'apparence de la feuille de propriétés.  
  
```  
void SetLook(
    PropSheetLook look,  
    int nNavControlWidth=100);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `look`  
 Une des valeurs d’énumération qui spécifie l’apparence de la feuille de propriétés. Le style par défaut pour une feuille de propriétés est `CMFCPropertySheet::PropSheetLook_Tabs`. Pour plus d’informations, consultez le tableau dans la section Notes de cette rubrique.  
  
 [in] `nNavControlWidth`  
 La largeur du contrôle de navigation, en pixels. La valeur par défaut est 100.  
  
### <a name="remarks"></a>Remarques  
 Pour afficher une feuille de propriétés dans un style autre que la valeur par défaut, appelez cette méthode avant de créer la fenêtre de la feuille de propriété.  
  
 Le tableau suivant répertorie les valeurs d’énumération qui peuvent être spécifiés dans le `look` paramètre.  
  
|Valeur|Description|  
|-----------|-----------------|  
|`CMFCPropertySheet::PropSheetLook_Tabs`|(Par défaut) Affiche un onglet pour chaque page de propriétés. Onglets sont affichés en haut de la feuille de propriétés et sont empilées s’il y a plus d’onglets que ceux qui tiennent sur une seule ligne.|  
|`CMFCPropertySheet::PropSheetLook_OutlookBar`|Affiche une liste des boutons de navigation, dans le style de la barre de Microsoft Outlook, sur le côté gauche de la feuille de propriétés. Chaque bouton de la liste correspond à une page de propriétés. L’infrastructure affiche des flèches de défilement s’il y a plus de boutons n’apparaissent pas dans la zone visible de la liste.|  
|`CMFCPropertySheet::PropSheetLook_Tree`|Affiche un contrôle d’arborescence sur le côté gauche de la feuille de propriétés. Chaque nœud parent ou enfant de l’arborescence correspond à une page de propriétés. L’infrastructure affiche des flèches de défilement s’il existe plus de nœuds ne peuvent pas être dans la zone visible du contrôle d’arborescence.|  
|`CMFCPropertySheet::PropSheetLook_OneNoteTabs`|Affiche un onglet, dans le style de Microsoft OneNote, pour chaque page de propriétés. Le framework affiche les onglets en haut de la feuille de propriétés et les flèches de défilement s’il y a plus d’onglets que qui tiennent sur une seule ligne.|  
|`CMFCPropertySheet::PropSheetLook_List`|Affiche une liste sur le côté gauche de la feuille de propriétés. Chaque élément de la liste correspond à une page de propriétés. L’infrastructure affiche des flèches de défilement s’il existe plusieurs éléments de liste n’apparaissent pas dans la zone visible de la liste.|  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyPage (classe)](../../mfc/reference/cmfcpropertypage-class.md)   
 [CMFCOutlookBar (classe)](../../mfc/reference/cmfcoutlookbar-class.md)

