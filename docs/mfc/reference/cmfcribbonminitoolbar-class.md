---
title: Classe de CMFCRibbonMiniToolBar | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar class
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7c69880578c0aba88a8463112f4d1e05f6032497
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar (classe)
Implémente une barre d'outils contextuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Constructeur par défaut.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Substitue `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Définit la liste des commandes à afficher sur la barre d'outils.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Affiche la mini-barre d'outils au niveau des coordonnées d'écran spécifiées.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Affiche la mini-barre d'outils avec un menu contextuel.|  
  
## <a name="remarks"></a>Remarques  
 La mini-barre d'outils s'affiche généralement après que l'utilisateur sélectionne un objet dans un document. Ainsi, quand l'utilisateur sélectionne un bloc de texte dans un programme de traitement de texte, l'application affiche une mini-barre d'outils qui contient des commandes de mise en forme de texte.  
  
 La mini-barre d'outils devient transparente quand le pointeur de la souris sort des limites de la mini-barre d'outils.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>CMFCRibbonMiniToolBar::SetCommands  
 Définit la liste des commandes à afficher sur la barre d'outils.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pRibbonBar`  
 La barre de ruban qui consiste à rechercher la mini barre d’outils pour les boutons à afficher.  
  
 [in] `lstCommands`  
 La liste des commandes pour afficher la mini barre d’outils. Toutes les catégories de ruban sont recherchés pour trouver les boutons associés.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour définir la liste des commandes s’affichent dans la barre d’outils.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `SetCommands` procédé de la `CMFCRibbonMiniToolBar` classe. Cet extrait de code fait partie de la [exemple de démonstration de MS Office 2007](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#9;](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>CMFCRibbonMiniToolBar::Show  
 Affiche la mini-barre d'outils au niveau des coordonnées d'écran spécifiées.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Spécifie la position horizontale de la mini barre d’outils en coordonnées d’écran.  
  
 [in] `y`  
 Spécifie la position verticale de la mini barre d’outils en coordonnées d’écran.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la barre d’outils miniature s’affiche avec succès ; dans le cas contraire, `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Affiche la mini-barre d'outils avec un menu contextuel.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `x`  
 Spécifie la position horizontale du menu contextuel en coordonnées d’écran.  
  
 [in] `y`  
 Spécifie la position verticale du menu contextuel en coordonnées d’écran.  
  
 [in] `uiMenuResID`  
 Spécifie l’ID de ressource du menu contextuel à afficher.  
  
 [in] `pWndOwner`  
 Identifie la fenêtre qui reçoit des messages dans le menu contextuel.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le menu contextuel s’affiche avec succès ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet d’afficher une mini barre d’outils qui possède un menu contextuel. Le menu contextuel se trouve à 15 pixels sous la mini barre d’outils.  
  
##  <a name="iscontextmenumode"></a>CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="isribbonminitoolbar"></a>CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

