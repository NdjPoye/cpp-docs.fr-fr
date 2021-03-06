---
title: CToolBar (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
dev_langs:
- C++
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a80ea4cb188d879b9af0a7901ffbe89b8673df6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ctoolbar-class"></a>CToolBar (classe)
Barres de contrôles contenant une ligne de boutons bitmap et des séparateurs facultatifs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CToolBar : public CControlBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CToolBar::CToolBar](#ctoolbar)|Construit un objet `CToolBar`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CToolBar::CommandToIndex](#commandtoindex)|Retourne l’index d’un bouton avec l’ID de commande donné.|  
|[CToolBar::Create](#create)|Crée la barre d’outils Windows et l’attache à le `CToolBar` objet.|  
|[CToolBar::CreateEx](#createex)|Crée un `CToolBar` objet avec les autres styles pour le texte incorporé `CToolBarCtrl` objet.|  
|[CToolBar::GetButtonInfo](#getbuttoninfo)|Récupère l’ID, le style et le numéro de l’image d’un bouton.|  
|[CToolBar::GetButtonStyle](#getbuttonstyle)|Récupère le style d’un bouton.|  
|[CToolBar::GetButtonText](#getbuttontext)|Récupère le texte qui apparaît sur un bouton.|  
|[CToolBar::GetItemID](#getitemid)|Retourne l’ID de commande d’un bouton ou un séparateur à l’index spécifié.|  
|[CToolBar::GetItemRect](#getitemrect)|Récupère le rectangle d’affichage pour l’élément à l’index spécifié.|  
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|Permet un accès direct au contrôle commun sous-jacent.|  
|[CToolBar::LoadBitmap](#loadbitmap)|Charge l’image bitmap qui contient les images de boutons bitmap.|  
|[CToolBar::LoadToolBar](#loadtoolbar)|Charge une ressource de barre d’outils créée avec l’éditeur de ressources.|  
|[CToolBar::SetBitmap](#setbitmap)|Définit une image bitmap.|  
|[CToolBar::SetButtonInfo associer](#setbuttoninfo)|Définit l’ID, le style et le numéro de l’image d’un bouton.|  
|[CToolBar::SetButtons](#setbuttons)|Jeux de bouton styles et un index d’images de boutons dans la bitmap.|  
|[CToolBar::SetButtonStyle](#setbuttonstyle)|Définit le style d’un bouton.|  
|[CToolBar::SetButtonText](#setbuttontext)|Définit le texte qui apparaît sur un bouton.|  
|[CToolBar::SetHeight](#setheight)|Définit la hauteur de la barre d’outils.|  
|[CToolBar::SetSizes](#setsizes)|Définit la taille des boutons et leurs images.|  
  
## <a name="remarks"></a>Notes  
 Les boutons peuvent fonctionner comme des boutons de commande, des boutons de case à cocher ou des cases d’option. `CToolBar` les objets sont généralement incorporés membres des objets de fenêtre frame dérivées de la classe [CFrameWnd](../../mfc/reference/cframewnd-class.md) ou [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md).  
  
 [CToolBar::GetToolBarCtrl](#gettoolbarctrl), une fonction membre new 4.0 de MFC, vous permet de tirer parti de la prise en charge du contrôle commun Windows pour la personnalisation de la barre d’outils et des fonctionnalités supplémentaires. `CToolBar` fonctions membres vous donnent la plupart des fonctionnalités des contrôles communs Windows ; Toutefois, lorsque vous appelez `GetToolBarCtrl`, vous pouvez donner à vos barres d’outils encore plus les caractéristiques des barres d’outils Windows 95/98. Lorsque vous appelez `GetToolBarCtrl`, il retourne une référence à un `CToolBarCtrl` objet. Consultez [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) pour plus d’informations sur la conception des barres d’outils à l’aide de contrôles communs Windows. Pour plus d’informations sur les contrôles communs, consultez [contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493) dans le Kit de développement logiciel Windows.  
  
 Visual C++ fournit deux méthodes pour créer une barre d’outils. Pour créer une ressource de barre d’outils à l’aide de l’éditeur de ressources, procédez comme suit :  
  
1.  Créer une ressource de barre d’outils.  
  
2.  Construire la `CToolBar` objet.  
  
3.  Appelez le [créer](#create) (ou [CreateEx](#createex)) afin de créer la barre d’outils Windows et l’attacher à la `CToolBar` objet.  
  
4.  Appelez [LoadToolBar](#loadtoolbar) pour charger la ressource de barre d’outils.  
  
 Dans le cas contraire, procédez comme suit :  
  
1.  Construire la `CToolBar` objet.  
  
2.  Appelez le [créer](#create) (ou [CreateEx](#createex)) afin de créer la barre d’outils Windows et l’attacher à la `CToolBar` objet.  
  
3.  Appelez [LoadBitmap](#loadbitmap) pour charger l’image bitmap qui contient les images de boutons de barre d’outils.  
  
4.  Appelez [SetButtons](#setbuttons) pour définir le style de bouton et associer chaque bouton avec une image dans la bitmap.  
  
 Toutes les images de bouton dans la barre d’outils proviennent d’une image bitmap, ce qui doit contenir une image pour chaque bouton. Toutes les images doivent être la même taille ; la valeur par défaut est 16 pixels de large et 15 pixels de haut. Images doivent être côte à côte dans la bitmap.  
  
 Le `SetButtons` fonction accepte un pointeur vers un tableau d’ID de contrôle et un entier qui spécifie le nombre d’éléments dans le tableau. La fonction définit l’ID de chaque bouton à la valeur de l’élément correspondant du tableau et attribue à chaque bouton un index d’image, qui spécifie la position de l’image du bouton dans l’image bitmap. Si un élément de tableau a la valeur **ID_SEPARATOR**, aucun index de l’image n’est attribué.  
  
 L’ordre des images dans la bitmap est généralement l’ordre dans lequel ils sont dessinés à l’écran, mais vous pouvez utiliser la [SetButtonInfo](#setbuttoninfo) (fonction) pour modifier la relation entre commande de l’image et l’ordre de dessin.  
  
 Tous les boutons dans une barre d’outils ont la même taille. La valeur par défaut est de 24 x 22 pixels, conformément aux *indications de l’Interface Windows pour la conception de logiciels*. L’espace supplémentaire entre les dimensions de l’image et le bouton est utilisé pour former une bordure autour de l’image.  
  
 Chaque bouton a une image. Les différentes bouton États et styles (enfoncé, vers le bas, désactivé, désactivé vers le bas et indéterminé) sont générés à partir d’une image. Bien que les images bitmap peuvent être n’importe quelle couleur, vous pouvez obtenir les meilleurs résultats avec des images en noir et en nuances de gris.  
  
> [!WARNING]
> `CToolBar` prend en charge les images bitmap avec un maximum de 16 couleurs. Lorsque vous chargez une image dans un éditeur de barre d’outils, Visual Studio automatiquement convertit l’image bitmap 16 couleurs, si nécessaire et affiche un message d’avertissement si l’image a été convertie. Si vous utilisez une image avec plus de 16 couleurs (à l’aide d’un éditeur externe pour modifier l’image), l’application peut se comporter de façon inattendue.  
  
 Boutons de barre d’outils imitant des boutons de commande par défaut. Toutefois, les boutons de barre d’outils peuvent également simuler un boutons de case à cocher ou les cases d’option. Boutons de case à cocher ont trois états : activé, effacés et indéterminé. Cases d’option ont uniquement deux états : activée et désactivée.  
  
 Pour définir un bouton ou un style de séparateur sans pointant vers un tableau, appelez [GetButtonStyle](#getbuttonstyle) pour récupérer le style, puis appelez [SetButtonStyle](#setbuttonstyle) au lieu de `SetButtons`. `SetButtonStyle` est particulièrement utile lorsque vous souhaitez modifier le style d’un bouton au moment de l’exécution.  
  
 Pour affecter le texte à afficher sur un bouton, appelez [GetButtonText](#getbuttontext) pour récupérer le texte pour apparaître sur le bouton, puis appeler [SetButtonText](#setbuttontext) pour définir le texte.  
  
 Pour créer un bouton de la case à cocher, affecter le style **TBBS_CHECKBOX** ou utilisez un `CCmdUI` l’objet `SetCheck` fonction membre dans une `ON_UPDATE_COMMAND_UI` gestionnaire. Appel de `SetCheck` devient un bouton de commande d’un bouton de la case à cocher. Passer `SetCheck` un argument de 0 pour désactivé, 1 pour activé, ou 2 pour indéterminé.  
  
 Pour créer un bouton radio, appelez une [CCmdUI](../../mfc/reference/ccmdui-class.md) l’objet [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) fonction membre d’un `ON_UPDATE_COMMAND_UI` gestionnaire. Passer `SetRadio` un argument de 0 pour différente de zéro pour activé ou désactivé. Pour fournir un comportement de mutuellement exclusifs d’un groupe de cases d’option, vous devez disposer `ON_UPDATE_COMMAND_UI` gestionnaires pour tous les boutons dans le groupe.  
  
 Pour plus d’informations sur l’utilisation de `CToolBar`, consultez l’article [implémentation de barre d’outils MFC](../../mfc/mfc-toolbar-implementation.md) et [Technical Note 31 : barres de contrôles](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CToolBar`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex  
 Cette fonction membre retourne l’index de la première barre d’outils bouton, en commençant à la position 0, dont l’ID de commande correspond à `nIDFind`.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDFind`  
 ID de commande d’un bouton de barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index du bouton, ou -1 si aucun bouton n’a l’ID de commande donné.  
  
##  <a name="create"></a>  CToolBar::Create  
 Cette fonction membre crée une barre d’outils de Windows (une fenêtre enfant) et l’associe le `CToolBar` objet.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,  
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers la fenêtre parente de la barre d’outils.  
  
 `dwStyle`  
 Le style de la barre d’outils. Styles de barre d’outils supplémentaires pris en charge sont :  
  
- `CBRS_TOP` Barre de contrôle est en haut de la fenêtre frame.  
  
- `CBRS_BOTTOM` Barre de contrôle est en bas de la fenêtre frame.  
  
- `CBRS_NOALIGN` Barre de contrôle n’est pas repositionné lorsque le parent est redimensionné.  
  
- `CBRS_TOOLTIPS` Barre de contrôle affiche des info-bulles.  
  
- **CBRS_SIZE_DYNAMIC** barre de contrôle est dynamique.  
  
- **CBRS_SIZE_FIXED** barre de contrôle est fixe.  
  
- **CBRS_FLOATING** barre de contrôle est flottant.  
  
- `CBRS_FLYBY` Barre d’état affiche des informations sur le bouton.  
  
- **CBRS_HIDE_INPLACE** barre de contrôle n’est pas affichée à l’utilisateur.  
  
 `nID`  
 ID de fenêtre enfant. de la barre d’outils  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Il définit également la hauteur de la barre d’outils sur une valeur par défaut.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]  
  
##  <a name="createex"></a>  CToolBar::CreateEx  
 Appelez cette fonction pour créer une barre d’outils de Windows (une fenêtre enfant) et l’associer avec le `CToolBar` objet.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,  
    CRect rcBorders = CRect(
    0, 
    0, 
    0, 
    0), 
    UINT nID = AFX_IDW_TOOLBAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers la fenêtre parente de la barre d’outils.  
  
 `dwCtrlStyle`  
 Styles supplémentaires pour la création de l’élément incorporé [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) objet. Par défaut, cette valeur est définie **TBSTYLE_FLAT**. Pour obtenir une liste complète des styles de barre d’outils, consultez `dwStyle`.  
  
 `dwStyle`  
 Le style de la barre d’outils. Consultez [contrôle de barre d’outils et les Styles de bouton](http://msdn.microsoft.com/library/windows/desktop/bb760439) dans le SDK Windows pour obtenir la liste des styles appropriés.  
  
 *rcBorders*  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui définit la largeur des bordures de la fenêtre de barre d’outils. Ces bordures sont définies 0,0,0,0 par défaut, ce qui entraîne une fenêtre de la barre d’outils sans bordures.  
  
 `nID`  
 ID de fenêtre enfant. de la barre d’outils  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Il définit également la hauteur de la barre d’outils sur une valeur par défaut.  
  
 Utilisez `CreateEx`, au lieu de [créer](#create), lorsque certains styles doivent être présentes au cours de la création du contrôle de barre d’outil incorporé. Par exemple, définissez `dwCtrlStyle` à **TBSTYLE_FLAT &#124; TBSTYLE_TRANSPARENT** pour créer une barre d’outils qui ressemble à la barre d’outils Internet Explorer 4.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]  
  
##  <a name="ctoolbar"></a>  CToolBar::CToolBar  
 Cette fonction membre construit un `CToolBar` de l’objet et définit la taille par défaut.  
  
```  
CToolBar();
```  
  
### <a name="remarks"></a>Notes  
 Appelez le [créer](#create) fonction membre pour créer la fenêtre de la barre d’outils.  
  
##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo  
 Cette fonction membre récupère l’ID de contrôle, le style et l’index de l’image du bouton de barre d’outils ou du séparateur à l’emplacement spécifié par *nIndex.*  
  
```  
void GetButtonInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& iImage) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index du bouton de barre d’outils ou du séparateur dont les informations sont à récupérer.  
  
 `nID`  
 Référence à un **UINT** qui est définie sur l’ID de commande du bouton.  
  
 `nStyle`  
 Référence à un **UINT** qui est défini sur le style du bouton.  
  
 `iImage`  
 Référence à un entier qui est défini à l’index de l’image du bouton dans la bitmap.  
  
### <a name="remarks"></a>Notes  
 Ces valeurs sont affectées aux variables référencées par `nID`, `nStyle`, et `iImage`. L’index d’image est la position de l’image dans la bitmap qui contient des images pour les boutons de barre d’outils. La première image est à la position 0.  
  
 Si `nIndex` spécifie un séparateur, `iImage` a la valeur de la largeur du séparateur en pixels.  
  
##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle  
 Appelez cette fonction membre pour récupérer le style d’un bouton ou un séparateur de la barre d’outils.  
  
```  
UINT GetButtonStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 L’index du style de bouton ou un séparateur de barre d’outils doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 Le style du bouton ou du séparateur spécifié par `nIndex`.  
  
### <a name="remarks"></a>Notes  
 Style d’un bouton détermine comment le bouton s’affiche et comment il répond aux entrées d’utilisateur. Consultez [SetButtonStyle](#setbuttonstyle) pour obtenir des exemples de styles de bouton.  
  
##  <a name="getbuttontext"></a>  CToolBar::GetButtonText  
 Appelez cette fonction membre pour récupérer le texte qui apparaît sur un bouton.  
  
```  
CString GetButtonText(int nIndex) const;  
  
void GetButtonText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de texte doit être récupéré.  
  
 `rString`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui contient le texte doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 A `CString` objet contenant le texte du bouton.  
  
### <a name="remarks"></a>Notes  
 La deuxième forme de ce membre fonction remplit un `CString` objet avec le texte de la chaîne.  
  
##  <a name="getitemid"></a>  CToolBar::GetItemID  
 Cette fonction membre retourne l’ID de commande du bouton ou du séparateur spécifié par `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’élément dont l’ID doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande du bouton ou du séparateur spécifié par `nIndex`.  
  
### <a name="remarks"></a>Notes  
 Retournent des séparateurs **ID_SEPARATOR**.  
  
##  <a name="getitemrect"></a>  CToolBar::GetItemRect  
 Cette fonction membre remplit la `RECT` structure dont l’adresse est contenue dans `lpRect` avec les coordonnées du bouton ou du séparateur spécifié par `nIndex`.  
  
```  
virtual void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’élément (bouton ou séparateur) dont coordonnées du rectangle doivent être récupérés.  
  
 `lpRect`  
 Adresse de la [RECT](../../mfc/reference/rect-structure1.md) structure qui contient les coordonnées de l’élément.  
  
### <a name="remarks"></a>Notes  
 Coordonnées sont exprimées en pixels par rapport au coin supérieur gauche de la barre d’outils.  
  
 Utilisez `GetItemRect` pour obtenir les coordonnées d’un séparateur que vous souhaitez remplacer par une zone de liste modifiable ou un autre contrôle.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CToolBar::SetSizes](#setsizes).  
  
##  <a name="gettoolbarctrl"></a>  CToolBar::GetToolBarCtrl  
 Cette fonction membre permet un accès direct au contrôle commun sous-jacent.  
  
```  
CToolBarCtrl& GetToolBarCtrl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à un objet `CToolBarCtrl`.  
  
### <a name="remarks"></a>Notes  
 Utilisez `GetToolBarCtrl` pour tirer parti des fonctionnalités du contrôle commun de barre d’outils Windows et pour tirer parti de la prise en charge [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) fournit pour la personnalisation de la barre d’outils.  
  
 Pour plus d’informations sur l’utilisation de contrôles communs, consultez l’article [contrôles](../../mfc/controls-mfc.md) et [contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493) dans le Kit de développement logiciel Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]  
  
##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap  
 Appelez cette fonction membre pour charger l’image bitmap spécifiée par `lpszResourceName` ou `nIDResource`.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResourceName`  
 Pointeur vers le nom de ressource de l’image bitmap à charger.  
  
 `nIDResource`  
 ID de ressource de l’image bitmap à charger.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 L’image bitmap doit contenir une image pour chaque bouton de barre d’outils. Si les images ne sont pas de la taille standard (16 pixels de large et 15 pixels de haut), appel [SetSizes](#setsizes) pour définir les tailles de bouton et de leurs images.  
  
> [!WARNING]
> `CToolBar` prend en charge les images bitmap avec un maximum de 16 couleurs. Lorsque vous chargez une image dans un éditeur de barre d’outils, Visual Studio automatiquement convertit l’image bitmap 16 couleurs, si nécessaire et affiche un message d’avertissement si l’image a été convertie. Si vous utilisez une image avec plus de 16 couleurs (à l’aide d’un éditeur externe pour modifier l’image), l’application peut se comporter de façon inattendue.  
  
##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar  
 Appelez cette fonction membre pour charger la barre d’outils spécifiée par `lpszResourceName` ou `nIDResource`.  
  
```  
BOOL LoadToolBar(LPCTSTR lpszResourceName);  
BOOL LoadToolBar(UINT nIDResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResourceName`  
 Pointeur vers le nom de ressource de la barre d’outils doit être chargé.  
  
 `nIDResource`  
 ID de ressource de la barre d’outils doit être chargé.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Consultez [éditeur de barre d’outils](../../windows/toolbar-editor.md) dans pour plus d’informations sur la création d’une ressource de barre d’outils.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CToolBar::CreateEx](#createex).  
  
##  <a name="setbitmap"></a>  CToolBar::SetBitmap  
 Appelez cette fonction membre pour définir l’image bitmap de la barre d’outils.  
  
```  
BOOL SetBitmap(HBITMAP hbmImageWell);
```  
  
### <a name="parameters"></a>Paramètres  
 *hbmImageWell*  
 Handle d’une image bitmap qui est associée à une barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Par exemple, appelez `SetBitmap` pour modifier l’image bitmap, une fois que l’utilisateur effectue une action sur un document qui modifie l’action d’un bouton.  
  
##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo associer  
 Appelez cette fonction membre pour définir l’ID de commande, le style et numéro de l’image du bouton.  
  
```  
void SetButtonInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int iImage);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du bouton ou séparateur pour lequel les informations sont à définir.  
  
 `nID`  
 La valeur à laquelle l’ID de commande du bouton est définie.  
  
 `nStyle`  
 Le nouveau style de bouton. Les styles de bouton suivants sont pris en charge :  
  
- **TBBS_BUTTON** pushbutton Standard (valeur par défaut)  
  
- **TBBS_SEPARATOR** séparateur  
  
- **TBBS_CHECKBOX** bouton de case à cocher automatiquement  
  
- **TBBS_GROUP** marque le début d’un groupe de boutons  
  
- **TBBS_CHECKGROUP** marque le début d’un groupe de boutons de case à cocher  
  
- **TBBS_DROPDOWN** crée un bouton de liste déroulante.  
  
- **TBBS_AUTOSIZE** la largeur du bouton sera calculée en fonction du texte du bouton, et non sur la taille de l’image.  
  
- **TBBS_NOPREFIX** le texte du bouton ne disposera d’un préfixe de l’accélérateur associé.  
  
 `iImage`  
 Nouvel index pour l’image du bouton dans la bitmap.  
  
### <a name="remarks"></a>Notes  
 Pour les séparateurs, qui ont le style **TBBS_SEPARATOR**, cette fonction épaisseur du séparateur en pixels pour la valeur stockée dans `iImage`.  
  
> [!NOTE]
>  Vous pouvez également définir les États de bouton à l’aide de la `nStyle` paramètre ; Toutefois, étant donné que les États de bouton sont contrôlées par le [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) gestionnaire, tout état vous définissez à l’aide de `SetButtonInfo` seront perdues lors du prochain inactif lors du traitement. Consultez [comment les objets d’Interface utilisateur de mise à jour](../../mfc/how-to-update-user-interface-objects.md) et [TN031 : barres de contrôles](../../mfc/tn031-control-bars.md) pour plus d’informations.  
  
 Pour plus d’informations sur les boutons et les images bitmap, consultez la [CToolBar](../../mfc/reference/ctoolbar-class.md) vue d’ensemble et [CToolBar::LoadBitmap](#loadbitmap).  
  
##  <a name="setbuttons"></a>  CToolBar::SetButtons  
 Cette fonction membre définit l’ID de commande de chaque bouton de barre d’outils à la valeur spécifiée par l’élément correspondant du tableau `lpIDArray`.  
  
```  
BOOL SetButtons(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpIDArray`  
 Pointeur vers un tableau d’ID de commande. Il peut être **NULL** pour allouer des boutons vide.  
  
 `nIDCount`  
 Nombre d’éléments dans le tableau vers lequel pointe `lpIDArray`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Si un élément du tableau a la valeur **ID_SEPARATOR**, un séparateur est créé dans la position correspondante de la barre d’outils. Cette fonction définit également le style de chaque bouton sur **TBBS_BUTTON** et le style de chaque séparateur à **TBBS_SEPARATOR**et assigne un index d’image pour chaque bouton. L’index d’image Spécifie la position de l’image du bouton dans la bitmap.  
  
 Vous n’avez pas besoin pour prendre en compte pour les séparateurs dans l’image bitmap, car cette fonction n’affecte pas les index d’image pour les séparateurs. Si la barre d’outils comporte des boutons aux positions 0, 1, 3 et un séparateur à la position 2, les images à 0, 1 et 2 des positions dans votre image bitmap assignés aux boutons aux positions 0, 1 et 3, respectivement.  
  
 Si `lpIDArray` est **NULL**, cette fonction alloue de l’espace pour le nombre d’éléments spécifié par `nIDCount`. Utilisez [SetButtonInfo](#setbuttoninfo) pour définir les attributs de chaque élément.  
  
##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle  
 Appelez cette fonction membre pour définir le style d’un bouton ou un séparateur, ou à des boutons du groupe.  
  
```  
void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index du bouton ou séparateur dont les informations sont à définir.  
  
 `nStyle`  
 Le style de bouton. Les styles de bouton suivants sont pris en charge :  
  
- **TBBS_BUTTON** pushbutton Standard (valeur par défaut)  
  
- **TBBS_SEPARATOR** séparateur  
  
- **TBBS_CHECKBOX** bouton de case à cocher automatiquement  
  
- **TBBS_GROUP** marque le début d’un groupe de boutons  
  
- **TBBS_CHECKGROUP** marque le début d’un groupe de boutons de case à cocher  
  
- **TBBS_DROPDOWN** crée un bouton de liste déroulante  
  
- **TBBS_AUTOSIZE** la largeur du bouton sera calculée en fonction du texte du bouton, et non sur la taille de l’image  
  
- **TBBS_NOPREFIX** le texte du bouton ne disposera d’un préfixe de l’accélérateur associé  
  
### <a name="remarks"></a>Notes  
 Style d’un bouton détermine comment le bouton s’affiche et comment il répond aux entrées d’utilisateur.  
  
 Avant d’appeler `SetButtonStyle`, appelez le [GetButtonStyle](#getbuttonstyle) fonction membre pour récupérer le style de bouton ou un séparateur.  
  
> [!NOTE]
>  Vous pouvez également définir les États de bouton à l’aide de la `nStyle` paramètre ; Toutefois, étant donné que les États de bouton sont contrôlées par le [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) gestionnaire, tout état vous définissez à l’aide de `SetButtonStyle` seront perdues lors du prochain inactif lors du traitement. Consultez [comment les objets d’Interface utilisateur de mise à jour](../../mfc/how-to-update-user-interface-objects.md) et [TN031 : barres de contrôles](../../mfc/tn031-control-bars.md) pour plus d’informations.  
  
##  <a name="setbuttontext"></a>  CToolBar::SetButtonText  
 Appelez cette fonction pour définir le texte sur un bouton.  
  
```  
BOOL SetButtonText(
    int nIndex,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index du bouton dont le texte doit être défini.  
  
 `lpszText`  
 Pointe vers le texte à définir sur un bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CToolBar::GetToolBarCtrl](#gettoolbarctrl).  
  
##  <a name="setheight"></a>  CToolBar::SetHeight  
 Cette fonction membre définit la hauteur de la barre d’outils à la valeur, en pixels, spécifié dans `cyHeight`.  
  
```  
void SetHeight(int cyHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 `cyHeight`  
 Hauteur en pixels de la barre d’outils.  
  
### <a name="remarks"></a>Notes  
 Après avoir appelé [SetSizes](#setsizes), utilisez cette fonction membre pour remplacer la hauteur de la barre d’outils standard. Si la hauteur est trop petite, les boutons seront découpés en bas.  
  
 Si cette fonction n’est pas appelée, le framework utilise la taille du bouton pour déterminer la hauteur de la barre d’outils.  
  
##  <a name="setsizes"></a>  CToolBar::SetSizes  
 Appelez cette fonction membre pour définir les boutons de la barre d’outils à la taille, en pixels, spécifié dans *sizeButton*.  
  
```  
void SetSizes(
    SIZE sizeButton,  
    SIZE sizeImage);
```  
  
### <a name="parameters"></a>Paramètres  
 *sizeButton*  
 La taille en pixels de chaque bouton.  
  
 `sizeImage`  
 La taille en pixels de chaque image.  
  
### <a name="remarks"></a>Notes  
 Le `sizeImage` paramètre doit contenir la taille, en pixels, des images bitmap de la barre d’outils. Les dimensions dans *sizeButton* doit être suffisante pour contenir l’image de plus de 7 supplémentaire en largeur et 6 pixels supplémentaires en hauteur. Cette fonction affecte également la hauteur de la barre d’outils pour tenir les boutons.  
  
 Appelez cette fonction membre uniquement pour les barres d’outils qui ne suivent pas *indications de l’Interface Windows pour la conception de logiciels* recommandations pour les tailles de bouton et d’image.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CTRLBARS](../../visual-cpp-samples.md)   
 [MFC exemple DLGCBR32](../../visual-cpp-samples.md)   
 [Exemple MFC DOCKTOOL](../../visual-cpp-samples.md)   
 [CControlBar (classe)](../../mfc/reference/ccontrolbar-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl (classe)](../../mfc/reference/ctoolbarctrl-class.md)   
 [CControlBar, classe](../../mfc/reference/ccontrolbar-class.md)
