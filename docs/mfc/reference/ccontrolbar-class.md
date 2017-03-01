---
title: CControlBar (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
dev_langs:
- C++
helpviewer_keywords:
- CControlBar class
- OLE resize bars
- OLE resize bars, base class
- dialog bars, base class
- toolbars [C++], base class
- control bars [C++], base class
- status bars, base class
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
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
ms.openlocfilehash: 9720c4c11656834923c0e42a2017d51543c08f53
ms.lasthandoff: 02/24/2017

---
# <a name="ccontrolbar-class"></a>CControlBar Class
La classe de base pour les classes de barre de contrôle [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), et [COleResizeBar](../../mfc/reference/coleresizebar-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|Construit un objet `CControlBar`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Retourne la taille d’une barre de contrôle dynamique comme un [CSize](../../atl-mfc-shared/reference/csize-class.md) objet.|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Retourne la taille de la barre de contrôle comme un [CSize](../../atl-mfc-shared/reference/csize-class.md) objet.|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|Retourne les dimensions actuelles de la zone de barre de contrôle ; y compris les bordures.|  
|[CControlBar::DoPaint](#dopaint)|Affiche les bordures et la barre de redimensionnement de la barre de contrôle.|  
|[CControlBar::DrawBorders](#drawborders)|Affiche les bordures de la barre de contrôle.|  
|[CControlBar::DrawGripper](#drawgripper)|Affiche la barre de redimensionnement de la barre de contrôle.|  
|[CControlBar::EnableDocking](#enabledocking)|Permet à une barre de contrôles ancrés ou flottants.|  
|[CControlBar::GetBarStyle](#getbarstyle)|Récupère les paramètres de style de barre de contrôle.|  
|[CControlBar::GetBorders](#getborders)|Récupère les valeurs de la bordure de la barre de contrôle.|  
|[CControlBar::GetCount](#getcount)|Retourne le nombre de non - `HWND` éléments dans la barre de contrôle.|  
|[CControlBar::GetDockingFrame](#getdockingframe)|Retourne un pointeur vers le frame auquel une barre de contrôle est ancrée.|  
|[CControlBar::IsFloating](#isfloating)|Retourne une valeur différente de zéro si la barre de contrôle en question est une barre de contrôle flottante.|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Appelle les gestionnaires d’interface utilisateur de commande.|  
|[Fonctions CControlBar::SetBarStyle](#setbarstyle)|Modifie les paramètres de style de barre de contrôle.|  
|[CControlBar::SetBorders](#setborders)|Définit les valeurs de la bordure de la barre de contrôle.|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Modifie le propriétaire de la place d’une barre de contrôle.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Si elle est différente de zéro, le `CControlBar` objet est supprimé lorsque la barre de contrôles Windows est détruite.|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Le propriétaire de la place de la barre de contrôle.|  
  
## <a name="remarks"></a>Remarques  
 Une barre de contrôle est une fenêtre qui est généralement alignée à gauche ou à droite d’une fenêtre frame. Il peut contenir des éléments enfants qui sont soit `HWND`- en fonction des contrôles, qui sont des fenêtres qui génèrent et répondent aux messages de Windows, ou non - `HWND`-en fonction des éléments qui ne sont pas windows et sont gérés par le code d’application ou le code d’infrastructure. Zones de liste et les contrôles d’édition sont des exemples de `HWND`- contrôles en fonction ; des volets de barre d’état et des boutons de bitmap sont des exemples de non - `HWND`-en fonction des contrôles.  
  
 Windows de la barre de contrôle sont généralement des fenêtres enfants d’une fenêtre frame parente et sont généralement des éléments frères de la vue du client ou du client MDI de la fenêtre frame. Un `CControlBar` objet utilise des informations sur le rectangle client de la fenêtre parente pour se positionner. Il informe ensuite la fenêtre parente à la quantité reste de l’espace non alloué dans la zone cliente de la fenêtre parente.  
  
 Pour plus d’informations sur `CControlBar`, voir :  
  
- [Barres de contrôles](../../mfc/control-bars.md)  
  
- [Note technique 31 : Les barres de contrôle](../../mfc/tn031-control-bars.md).  
  
-   L’article de la Base de connaissances Q242577 : PRB : mise à jour de commande UI gestionnaires ne fonctionnent pas pour le Menu associé à une boîte de dialogue  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="a-namecalcdynamiclayouta--ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 L’infrastructure appelle cette fonction membre pour calculer les dimensions d’une barre d’outils dynamique.  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nLength`  
 De la barre de contrôle, horizontale ou verticale, en fonction de la dimension demandée `dwMode`.  
  
 `nMode`  
 Les indicateurs prédéfinis suivants sont utilisés pour déterminer la hauteur et la largeur de la barre de contrôle dynamique. Utilisez l’opérateur de bits OR (|) pour combiner les indicateurs.  
  
|Indicateurs de mode de disposition|Signification|  
|-----------------------|-------------------|  
|`LM_STRETCH`|Indique si la barre de contrôle doit être étirée pour la taille de l’image. Définir si la barre n’est pas une barre d’ancrage (non disponible pour l’ancrage). Pas définie si la barre est ancrés ou flottants (disponible d’ancrage). Si la valeur, `LM_STRETCH` ignore `nLength` et retourne les dimensions basées sur les `LM_HORZ` état. `LM_STRETCH`fonctionne de façon similaire à la `bStretch` paramètre utilisé dans [CalcFixedLayout](#calcfixedlayout); voir cette fonction membre pour plus d’informations sur la relation entre l’étirement et l’orientation.|  
|`LM_HORZ`|Indique que la barre est orientée horizontalement ou verticalement. Définit si la barre est orientée horizontalement, et s’il est orienté verticalement, il n’est pas définie. `LM_HORZ`fonctionne de façon similaire à la `bHorz` paramètre utilisé dans [CalcFixedLayout](#calcfixedlayout); voir cette fonction membre pour plus d’informations sur la relation entre l’étirement et l’orientation.|  
|**LM_MRUWIDTH**|Utilisés le plus récemment largeur dynamique. Ignore `nLength` paramètre et utilise le mémorisés utilisés le plus récemment largeur.|  
|`LM_HORZDOCK`|Horizontal ancré Dimensions. Ignore `nLength` paramètre et retourne la taille dynamique avec la plus grande largeur.|  
|`LM_VERTDOCK`|Vertical ancré Dimensions. Ignore `nLength` paramètre et retourne la taille dynamique avec la plus grande hauteur.|  
|`LM_LENGTHY`|Définir si `nLength` indique la hauteur (axe Y) au lieu de largeur.|  
|`LM_COMMIT`|Réinitialise **LM_MRUWIDTH** à la largeur actuelle de la barre de contrôle flottante.|  
  
### <a name="return-value"></a>Valeur de retour  
 La barre de contrôle la taille, en pixels, d’une [CSize](../../atl-mfc-shared/reference/csize-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction membre pour fournir votre propre disposition dynamique dans les classes dérivées de `CControlBar`. Classes MFC dérivées de `CControlBar`, tel que [CToolbar](../../mfc/reference/ctoolbar-class.md), remplacez cette fonction membre et de fournir leur propre implémentation.  
  
##  <a name="a-namecalcfixedlayouta--ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 Appelez cette fonction membre pour calculer la taille horizontale d’une barre de contrôle.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Paramètres  
 `bStretch`  
 Indique si la barre doit être étirée pour la taille de l’image. Le `bStretch` paramètre est différente de zéro lorsque la barre n’est pas une barre d’ancrage (non disponible pour la station d’accueil) et 0 lorsqu’elle est ancrée ou flottante (disponible d’ancrage).  
  
 `bHorz`  
 Indique que la barre est orientée horizontalement ou verticalement. Le `bHorz` paramètre est différent de zéro si la barre est orientée horizontalement et 0 s’il est orienté verticalement.  
  
### <a name="return-value"></a>Valeur de retour  
 La barre de contrôle la taille, en pixels, d’une `CSize` objet.  
  
### <a name="remarks"></a>Remarques  
 Barres de contrôle, telles que des barres d’outils peuvent être étirés horizontalement ou verticalement pour accueillir les boutons figurant dans la barre de contrôle.  
  
 Si `bStretch` est **TRUE**, étirer la dimension de l’orientation fournie par `bHorz`. En d’autres termes, si `bHorz` est **FALSE**, la barre de contrôle est étirée verticalement. Si `bStretch` est **FALSE**, aucune extension se produit. Le tableau suivant montre les permutations possibles et les styles de barre de contrôle qui en résulte, de `bStretch` et `bHorz`.  
  
|bStretch|bHorz|Étirer|Orientation|Ne pas d’ancrage d’ancrage|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**TRUE**|**TRUE**|Étirement horizontal|Orientation horizontale|Pas d’ancrage|  
|**TRUE**|**FALSE**|Étirement vertical|Orientation verticale|Pas d’ancrage|  
|**FALSE**|**TRUE**|Aucun étirement disponibles|Orientation horizontale|Ancrage|  
|**FALSE**|**FALSE**|Aucun étirement disponibles|Orientation verticale|Ancrage|  
  
##  <a name="a-namecalcinsiderecta--ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 L’infrastructure appelle cette fonction pour calculer la zone cliente de la barre de contrôle.  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Contient les dimensions actuelles de la barre de contrôle ; y compris les bordures.  
  
 `bHorz`  
 Indique que la barre est orientée horizontalement ou verticalement. Le `bHorz` paramètre est différent de zéro si la barre est orientée horizontalement et 0 s’il est orienté verticalement.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est appelée avant que la barre de contrôle est peint.  
  
 Remplacez cette fonction pour personnaliser le rendu de la bordure et la barre de redimensionnement du contrôle.  
  
##  <a name="a-nameccontrolbara--ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar  
 Construit un objet `CControlBar`.  
  
```  
CControlBar();
```  
  
##  <a name="a-namedopainta--ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint  
 Appelé par l’infrastructure pour afficher les bordures et la barre de redimensionnement du contrôle.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointe vers le contexte de périphérique à utiliser pour le rendu de la bordure et la barre de redimensionnement de la barre de contrôle.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour personnaliser le comportement de dessin de la barre de contrôle.  
  
 Une autre méthode de personnalisation consiste à substituer les `DrawBorders` et `DrawGripper` les fonctions et ajouter du code de dessin personnalisé pour les bordures et la barre de redimensionnement. Étant donné que ces méthodes sont appelées par la valeur par défaut `DoPaint` (méthode), une substitution de `DoPaint` n’est pas nécessaire.  
  
##  <a name="a-namedrawbordersa--ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders  
 Appelé par l’infrastructure pour afficher les bordures de la barre de contrôle.  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointe vers le contexte de périphérique à utiliser pour le rendu de la bordure de la barre de contrôle.  
  
 `rect`  
 Un `CRect` objet qui contient les dimensions de la barre de contrôle.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction pour personnaliser l’apparence des bordures de barre de contrôle.  
  
##  <a name="a-namedrawgrippera--ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper  
 Appelé par l’infrastructure pour afficher la barre de redimensionnement de la barre de contrôle.  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointe vers le contexte de périphérique à utiliser pour le rendu de la barre de redimensionnement de barre de contrôle.  
  
 `rect`  
 Un `CRect` objet qui contient les dimensions de la barre de redimensionnement de barre de contrôle.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction pour personnaliser l’apparence de la barre de redimensionnement de barre de contrôle.  
  
##  <a name="a-nameenabledockinga--ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::EnableDocking  
 Appelez cette fonction pour activer une barre de contrôle ancré.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDockStyle`  
 Spécifie si la barre de contrôle prend en charge d’ancrage et les côtés de la fenêtre parente à laquelle la barre de contrôle peut être ancrée, si pris en charge. Peut être une ou plusieurs des opérations suivantes :  
  
- `CBRS_ALIGN_TOP`Permet d’ancrage en haut de la zone cliente.  
  
- `CBRS_ALIGN_BOTTOM`Permet d’ancrage en bas de la zone cliente.  
  
- `CBRS_ALIGN_LEFT`Permet d’ancrage sur le côté gauche de la zone cliente.  
  
- `CBRS_ALIGN_RIGHT`Permet d’ancrage située à droite de la zone cliente.  
  
- `CBRS_ALIGN_ANY`Autorise la fixation sur n’importe quel côté de la zone cliente.  
  
- `CBRS_FLOAT_MULTI`Permet à plusieurs barres de contrôles à flotter dans une fenêtre mini-frame unique.  
  
 La valeur 0 (autrement dit, n’indiquant aucun indicateur), la barre de contrôle ne sera pas ancrer.  
  
### <a name="remarks"></a>Remarques  
 Les côtés spécifiées doivent correspondre à un des côtés activées pour l’ancrage de la fenêtre frame de destination, ou la barre de contrôle ne peut pas être ancrée à cette fenêtre frame.  
  
##  <a name="a-namegetbarstylea--ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>CControlBar::GetBarStyle  
 Appelez cette fonction pour déterminer quel **CBRS_** (styles de barre de contrôle) paramètres sont actuellement définis pour la barre de contrôle.  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Actuel **CBRS_** (styles de barre de contrôle) des paramètres de la barre de contrôle. Consultez la page [fonctions CControlBar::SetBarStyle](#setbarstyle) pour une liste complète des styles disponibles.  
  
### <a name="remarks"></a>Notes  
 Ne gère pas **WS_** (fenêtre) de style.  
  
##  <a name="a-namegetbordersa--ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders  
 Retourne les valeurs actuelles de la bordure de la barre de contrôle.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CRect` objet qui contient la largeur (en pixels) de chaque côté d’une barre de contrôle. Par exemple, la valeur de la `left` membre, de [CRect](../../atl-mfc-shared/reference/crect-class.md) d’objet, la largeur de la bordure gauche.  
  
##  <a name="a-namegetcounta--ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount  
 Retourne le nombre de non - `HWND` sur les éléments de la `CControlBar` objet.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de non - `HWND` sur les éléments de la `CControlBar` objet. Cette fonction renvoie la valeur 0 pour un [CDialogBar](../../mfc/reference/cdialogbar-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Le type de l’élément dépend de l’objet dérivé : volets pour [CStatusBar](../../mfc/reference/cstatusbar-class.md) objets et des boutons et des séparateurs pour [CToolBar](../../mfc/reference/ctoolbar-class.md) objets.  
  
##  <a name="a-namegetdockingframea--ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 Appelez cette fonction membre pour obtenir un pointeur vers la fenêtre frame actuelle à laquelle votre barre de contrôle est ancré.  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers une fenêtre frame en cas de réussite ; dans le cas contraire **NULL**.  
  
 Si la barre de contrôle n’est pas ancrée à une fenêtre frame (autrement dit, si la barre de contrôle est flottant), cette fonction retourne un pointeur à son parent [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur les barres de contrôle ancrable, consultez [CControlBar::EnableDocking](#enabledocking) et [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
##  <a name="a-nameisfloatinga--ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating  
 Appelez cette fonction membre pour déterminer si la barre de contrôle est flottant ou ancré.  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la barre de contrôle est flottante. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Pour modifier l’état d’une barre de contrôle d’ancrée en virgule flottante, appelez [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).  
  
##  <a name="a-namembautodeletea--ccontrolbarmbautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 Si elle est différente de zéro, le `CControlBar` objet est supprimé lorsque la barre de contrôles Windows est détruite.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Remarques  
 `m_bAutoDelete`est une variable publique de type **BOOL**.  
  
 Un objet de barre de contrôle est généralement incorporé dans un objet fenêtre frame. Dans ce cas, `m_bAutoDelete` est 0, car l’objet de la barre de contrôle incorporé est détruit lorsque la fenêtre frame est détruite.  
  
 Définissez cette variable sur une valeur différente de zéro si vous allouez un `CControlBar` objet sur le tas et que vous n’envisagez pas d’appeler **supprimer**.  
  
##  <a name="a-namempinplaceownera--ccontrolbarmpinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 Le propriétaire de la place de la barre de contrôle.  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="a-nameonupdatecmduia--ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 Cette fonction membre est appelée par l’infrastructure pour mettre à jour l’état de la barre d’état ou de la barre d’outils.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pTarget`  
 Pointe vers la fenêtre frame principale de l’application. Ce pointeur est utilisé pour router des messages de mise à jour.  
  
 `bDisableIfNoHndler`  
 Indicateur qui indique si un contrôle qui ne possède aucun gestionnaire de mise à jour doit être affiché automatiquement désactivé.  
  
### <a name="remarks"></a>Remarques  
 Pour mettre à jour un volet ou des boutons, utiliser le `ON_UPDATE_COMMAND_UI` macro dans votre table des messages pour définir un gestionnaire de mise à jour de façon appropriée. Consultez la page [ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4) pour plus d’informations sur l’utilisation de cette macro.  
  
 `OnUpdateCmdUI`est appelé par l’infrastructure lorsque l’application est inactive. La fenêtre frame à mettre à jour doit être au moins indirectement, une fenêtre enfant d’une fenêtre frame visible. `OnUpdateCmdUI`avancée substituable.  
  
##  <a name="a-namesetbarstylea--ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>Fonctions CControlBar::SetBarStyle  
 Appelez cette fonction pour définir l’élément **CBRS_** les styles de la barre de contrôle.  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Les styles de votre choisis pour la barre de contrôle. Peut être une ou plusieurs des opérations suivantes :  
  
- `CBRS_ALIGN_TOP`Permet à la barre de contrôle pour être ancré en haut de la zone cliente d’une fenêtre frame.  
  
- `CBRS_ALIGN_BOTTOM`Permet à la barre de contrôle pour être ancrée au bas de la zone cliente d’une fenêtre frame.  
  
- `CBRS_ALIGN_LEFT`Permet à la barre de contrôle pour être ancré à gauche de la zone cliente d’une fenêtre frame.  
  
- `CBRS_ALIGN_RIGHT`Permet à la barre de contrôle pour être ancré à droite de la zone cliente d’une fenêtre frame.  
  
- `CBRS_ALIGN_ANY`Permet à la barre de contrôle pour être ancré à n’importe quel côté de la zone cliente d’une fenêtre frame.  
  
- `CBRS_BORDER_TOP`Provoque une bordure à dessiner sur le bord supérieur de la barre de contrôle lorsqu’il est visible.  
  
- `CBRS_BORDER_BOTTOM`Provoque une bordure à dessiner sur le bord inférieur de la barre de contrôle lorsqu’il est visible.  
  
- `CBRS_BORDER_LEFT`Provoque une bordure à dessiner sur le bord gauche de la barre de contrôle lorsqu’il est visible.  
  
- `CBRS_BORDER_RIGHT`Provoque une bordure à dessiner sur le bord droit de la barre de contrôle lorsqu’il est visible.  
  
- `CBRS_FLOAT_MULTI`Permet à plusieurs barres de contrôles à flotter dans une fenêtre mini-frame unique.  
  
- `CBRS_TOOLTIPS`Provoque l’info-bulles à afficher pour la barre de contrôle.  
  
- `CBRS_FLYBY`Provoque le texte du message à mettre à jour en même temps que les info-bulles.  
  
- **CBRS_GRIPPER** provoque une barre de redimensionnement, semblable à celle utilisée sur les bandes dans un **CReBar** à dessiner pour tout objet `CControlBar`-classe dérivée.  
  
### <a name="remarks"></a>Notes  
 N’affecte pas la **WS_** les paramètres (style de fenêtre).  
  
##  <a name="a-namesetbordersa--ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders  
 Appelez cette fonction pour définir la taille des bordures de la barre contrôle.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 *cxLeft*  
 La largeur (en pixels) de la bordure gauche de la barre de contrôle.  
  
 *cyTop*  
 La hauteur (en pixels) de la bordure supérieure de la barre de contrôle.  
  
 *cxRight*  
 La largeur (en pixels) de la bordure droite de la barre de contrôle.  
  
 *cyBottom*  
 La hauteur (en pixels) de la bordure inférieure de la barre contrôle.  
  
 `lpRect`  
 Un pointeur vers un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui contient la largeur (en pixels) de chaque bordure de l’objet de barre de contrôle.  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit les bordures supérieure et inférieure de la barre de contrôle de 5 pixels et les bordures gauche et droite de 2 pixels :  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#61;](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="a-namesetinplaceownera--ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 Modifie le propriétaire de la place d’une barre de contrôle.  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Un pointeur vers un `CWnd` objet.  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CToolBar (classe)](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar (classe)](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar (classe)](../../mfc/reference/cstatusbar-class.md)   
 [CReBar (classe)](../../mfc/reference/crebar-class.md)

