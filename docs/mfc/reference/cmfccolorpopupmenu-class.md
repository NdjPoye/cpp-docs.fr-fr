---
title: Classe de CMFCColorPopupMenu | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu class
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14076d78eaf86ef01e68656685dd2fd102d96311
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu (classe)
Représente un menu contextuel sélectionner des couleurs dans un document ou une application permettant aux utilisateurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Construit un objet `CMFCColorPopupMenu`.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Crée une barre de couleur ancrable détachables. (Substitue [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Retourne le [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) qui est incorporé dans le menu contextuel. (Substitue [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Définit l’objet de contrôle de grille de propriété de l’élément incorporé `CMFCColorBar` objet.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`m_bEnabledInCustomizeMode`|Valeur booléenne qui détermine s’il faut afficher la barre de couleurs.|  
|`m_wndColorBar`|Le `CMFCColorBar` objet qui fournit la sélection de couleur.|  
  
### <a name="remarks"></a>Notes  
 Cette classe hérite de la fonctionnalité de menu contextuel de la `CMFCPopupMenu` classe et gère un `CMFCColorBar` objet qui fournit la sélection de couleur. Lorsque l’infrastructure de la barre d’outils est en mode de personnalisation et le `m_bEnabledInCustomizeMode` membre a la valeur `FALSE`, l’objet de barre de couleur n’est pas affiché. Pour plus d’informations sur le mode de personnalisation, consultez [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Pour plus d’informations sur `CMFCColorBar`, consultez [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcolorpopupmenu.h  
  
##  <a name="a-namecmfccolorpopupmenua--cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu  
 Construit un objet `CMFCColorPopupMenu`.  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `colors`  
 Tableau de couleurs que le framework affiche dans le menu contextuel.  
  
 [in] `color`  
 La couleur sélectionnée par défaut.  
  
 [in] `lpszAutoColor`  
 L’étiquette de texte de la *automatique* bouton de couleur (par défaut), ou `NULL`.  
  
 L’étiquette du bouton automatique standard est **automatique**.  
  
 [in] `lpszOtherColor`  
 L’étiquette de texte de la *autres* bouton qui affiche un plus grand choix de couleurs, ou `NULL`.  
  
 L’étiquette du bouton autres standard est **plus de couleurs... **.  
  
 [in] `lpszDocColors`  
 L’étiquette de texte du bouton de couleurs du document. La palette de couleurs du document répertorie toutes les couleurs que le document utilise actuellement.  
  
 [in] `lstDocColors`  
 Une liste de couleurs que le document utilise actuellement.  
  
 [in] `nColumns`  
 Le nombre de colonnes qui possède le tableau de couleurs.  
  
 [in] `nHorzDockRows`  
 Le nombre de lignes de la barre de couleur lorsqu’elle est ancrée horizontalement.  
  
 [in] `nVertDockColumns`  
 Le nombre de colonnes de la barre de couleur lorsqu’elle est ancrée verticalement.  
  
 [in] `colorAutomatic`  
 La couleur par défaut que le framework s’applique lorsque vous cliquez sur le bouton automatique.  
  
 [in] `uiCommandID`  
 ID de la commande de contrôle de barre de couleur.  
  
 [in] `bStdColorDlg`  
 Valeur booléenne qui indique s’il faut afficher la boîte de dialogue couleur système standard ou [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) boîte de dialogue.  
  
 [in] `pParentBtn`  
 Pointeur vers un bouton parent.  
  
 [in] `nID`  
 ID de la commande.  
  
### <a name="remarks"></a>Notes  
 Chaque surcharge de constructeur définit les `m_bEnabledInCustomizeMode` membre à `FALSE`.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCColorPopupMenu` objet.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#34;](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="a-namecreatetearoffbara--cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar  
 Crée une barre de couleur ancrable détachables.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pWndMain`|Pointeur vers la fenêtre parente de la barre à détacher.|  
|[in] `uiID`|L’ID de commande de la barre à détacher.|  
|[in] `lpszName`|Le texte de la fenêtre de la barre à détacher.|  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le nouvel objet de barre de contrôle détachables.  
  
### <a name="remarks"></a>Notes  
 Cette méthode crée un [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) de l’objet et le caste en un [CPane classe](../../mfc/reference/cpane-class.md) pointeur. Vous pouvez convertir cette valeur en un [CMFCColorBar classe](../../mfc/reference/cmfccolorbar-class.md) pointeur en utilisant l’une des macros de conversion décrites dans [conversion Type des objets de classe MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="a-namegetmenubara--cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>CMFCColorPopupMenu::GetMenuBar  
 Retourne le [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) qui est incorporé dans le menu contextuel.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers les données incorporées `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Remarques  
 Le menu contextuel couleur a incorporé [CMFCPopupMenuBar classe](../../mfc/reference/cmfcpopupmenubar-class.md) objet. Substituez cette méthode dans une classe dérivée si votre application utilise un autre type incorporé.  
  
##  <a name="a-namesetproplista--cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>CMFCColorPopupMenu::SetPropList  
 Définit l’objet de contrôle de grille de propriété de l’élément incorporé `CMFCColorBar` objet.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndList`  
 Pointeur vers un objet de contrôle de grille de propriétés.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

