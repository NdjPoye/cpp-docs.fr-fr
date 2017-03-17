---
title: Classe de CMFCDropDownFrame | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame class
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f045e4a3b580f12e64758737495c32963bea6db
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame (classe)
Fournit une fonctionnalité de fenêtre frame de la liste déroulante pour les barres d’outils de la liste déroulante et les boutons de barre d’outils de la liste déroulante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Constructeur par défaut.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDropDownFrame::Create](#create)|Crée un objet `CMFCDropDownFrame`.|  
|`CMFCDropDownFrame::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Récupère la barre de menu parent de l’image de la liste déroulante.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Récupère le menu contextuel du parent de l’image de la liste déroulante.|  
|`CMFCDropDownFrame::GetThisClass`|Utilisé par le framework d’obtenir un pointeur vers le [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objet associé à ce type de classe.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Repositionne le cadre de la liste déroulante.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Définit si la fenêtre de la barre d’outils déroulante enfant est supprimée automatiquement.|  
  
### <a name="remarks"></a>Notes  
 Cette classe n’est pas destinée à être utilisée directement à partir de votre code.  
  
 L’infrastructure utilise cette classe pour fournir un comportement frame le `CMFCDropDownToolbar` et `CMFCDropDownToolbarButton` classes. Pour plus d’informations sur ces classes, consultez [CMFCDropDownToolBar classe](../../mfc/reference/cmfcdropdowntoolbar-class.md) et [CMFCDropDownToolbarButton classe](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment récupérer un pointeur vers un `CMFCDropDownFrame` de l’objet d’un `CFrameWnd` (classe) et comment définir l’enfant de fenêtre de la barre d’outils de la liste déroulante d’être détruites automatiquement.  
  
 [!code-cpp[NVC_MFC_RibbonApp n °&36;](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdropdowntoolbar.h  
  
##  <a name="create"></a>CMFCDropDownFrame::Create  
 Crée un objet `CMFCDropDownFrame`.  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `pWndParent`|La fenêtre parente de l’image de la liste déroulante.|  
|[in] `x`|Coordonnée d’écran horizontale pour l’emplacement de l’image du bas vers le bas.|  
|[in] `y`|Coordonnée d’écran verticale de l’emplacement de l’image du bas vers le bas.|  
|[in] `pWndOriginToolbar`|La barre d’outils affiche les boutons de liste déroulante utilisée par cette méthode pour remplir le nouvel objet de frame de la liste déroulante.|  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le cadre de la liste déroulante a été créé avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode appelle la base de [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) pour créer la fenêtre de liste déroulante avec la `WS_POPUP` style. La fenêtre frame de la liste déroulante apparaît en coordonnées d’écran spécifiées. Cette méthode échoue si le [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) méthode renvoie `FALSE`.  
  
 Le `CMFCDropDownFrame` classe crée une copie de le `CMFCDropDownToolBar` paramètre. Cette méthode copie les images des boutons et les États de bouton à partir de la `pWndOriginToolbar` paramètre à le `m_pWndOriginToolbar` membre de données.  
  
##  <a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar  
 Récupère la barre de menu parent de l’image de la liste déroulante.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la barre de menu parent de l’image de la liste déroulante, ou `NULL` si le frame n’a aucun parent.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode récupère la barre de menus du parent à partir du bouton parent. Cette méthode retourne `NULL` si le cadre de la liste déroulante n’a pas de bouton parent ou le bouton parent aucune barre de menu parent.  
  
##  <a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu  
 Récupère le menu contextuel du parent de l’image de la liste déroulante.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le menu déroulant parent de l’image de la liste déroulante, ou `NULL` si le frame n’a aucun parent.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode récupère le menu parent à partir du bouton parent. Cette méthode retourne `NULL` si le cadre de la liste déroulante n’a pas de bouton parent ou le bouton parent aucun menu parent.  
  
##  <a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout  
 Repositionne le cadre de la liste déroulante.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|[in] `bNotify`|Non utilisé.|  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette méthode lorsque l’image de la liste déroulante est créée ou la fenêtre parent est redimensionnée. Cette méthode calcule la position et la taille de l’image de la liste déroulante à l’aide de la position et la taille de la fenêtre parente.  
  
##  <a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy  
 Définit si la fenêtre de la barre d’outils déroulante enfant est supprimée automatiquement.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bAutoDestroy`  
 `TRUE`Pour détruire automatiquement la fenêtre de la barre d’outils déroulante associée. dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Si `bAutoDestroy` est `TRUE`, le `CMFCDropDownFrame` destructeur détruit la fenêtre de la barre d’outils déroulante associée. La valeur par défaut est `TRUE`.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe de CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton (classe)](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

