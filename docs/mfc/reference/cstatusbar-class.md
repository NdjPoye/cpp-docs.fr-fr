---
title: CStatusBar (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
dev_langs:
- C++
helpviewer_keywords:
- indicators, status bar
- CStatusBar class
- status bars
- indicators
- status indicators
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e96070041ef5bcee0865991a14b6484082d8fc91
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbar-class"></a>CStatusBar (classe)
Barre de contrôles avec une ligne de volets de sortie de texte ou « indicateurs ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|Construit un objet `CStatusBar`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|Obtient l’index pour un ID d’indicateur donné.|  
|[CStatusBar::Create](#create)|Crée la barre d’état, l’attache à le `CStatusBar` de l’objet et définit la hauteur de police et barre initiale.|  
|[CStatusBar::CreateEx](#createex)|Crée un `CStatusBar` objet avec des styles supplémentaires pour les données incorporées `CStatusBarCtrl` objet.|  
|[CStatusBar::DrawItem](#drawitem)|Appelé lorsqu’un aspect visuel d’un dessin propriétaire de la barre d’état contrôle change.|  
|[CStatusBar::GetItemID](#getitemid)|Obtient l’ID d’indicateur pour un index donné.|  
|[CStatusBar::GetItemRect](#getitemrect)|Obtient affiche un rectangle pour un index donné.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Obtient l’ID d’indicateur de style et la largeur d’un index donné.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Obtient le style d’indicateur pour un index donné.|  
|[CStatusBar::GetPaneText](#getpanetext)|Obtient le texte de l’indicateur d’un index donné.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Permet d’accéder directement au contrôle commun sous-jacent.|  
|[CStatusBar::SetIndicators](#setindicators)|Définit l’ID de l’indicateur.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Définit l’ID d’indicateur, le style et la largeur d’un index donné.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Définit le style d’indicateur pour un index donné.|  
|[CStatusBar::SetPaneText](#setpanetext)|Définit le texte de l’indicateur d’un index donné.|  
  
## <a name="remarks"></a>Remarques  
 Les volets de sortie sont fréquemment utilisés comme lignes de messages et comme indicateurs d’état. Exemples : les lignes de message à l’aide de menu qui décrivent brièvement la commande de menu sélectionné et les indicateurs qui indiquent l’état de l’arrêt défil, VERR. NUM et autres clés.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), une fonction membre de nouveau sur la version 4.0 de MFC, vous permet de tirer parti de la prise en charge du contrôle commun Windows pour la personnalisation et des fonctionnalités supplémentaires de la barre d’état. `CStatusBar`fonctions membres vous donnent la plupart des fonctionnalités des contrôles communs Windows ; Toutefois, lorsque vous appelez `GetStatusBarCtrl`, vous pouvez donner à vos barres d’état encore plus des caractéristiques d’une barre d’état Windows 95/98. Lorsque vous appelez `GetStatusBarCtrl`, il retourne une référence à un `CStatusBarCtrl` objet. Consultez la page [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) pour plus d’informations sur la conception de barres d’outils à l’aide des contrôles communs Windows. Pour plus d’informations sur les contrôles communs, consultez [contrôles communs](http://msdn.microsoft.com/library/windows/desktop/bb775493) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Le framework stocke les informations de l’indicateur dans un tableau avec l’indicateur à l’extrême gauche à la position 0. Lorsque vous créez une barre d’état, vous utilisez un tableau de chaînes d’ID de l’infrastructure associe les indicateurs correspondants. Vous pouvez ensuite utiliser un ID de chaîne ou un index pour accéder à un indicateur.  
  
 Par défaut, le premier indicateur est « flexible » : il occupe la longueur de la barre d’état non utilisée par les autres volets d’indicateur, afin que les autres volets sont alignés à droite.  
  
 Pour créer une barre d’état, procédez comme suit :  
  
1.  Construire la `CStatusBar` objet.  
  
2.  Appelez le [créer](#create) (ou [CreateEx](#createex)) (fonction) pour créer la fenêtre de la barre d’état et l’attacher à la `CStatusBar` objet.  
  
3.  Appelez [SetIndicators](#setindicators) à associer un ID de chaîne à chaque indicateur.  
  
 Il existe trois façons de mettre à jour le texte dans un volet de barre d’état :  
  
1.  Appelez [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) pour mettre à jour le texte dans le volet 0.  
  
2.  Appelez [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) dans la barre d’état `ON_UPDATE_COMMAND_UI` gestionnaire.  
  
3.  Appelez [SetPaneText](#setpanetext) pour mettre à jour le texte d’un volet.  
  
 Appelez [SetPaneStyle](#setpanestyle) pour mettre à jour le style d’un volet de barre d’état.  
  
 Pour plus d’informations sur l’utilisation de `CStatusBar`, consultez l’article [implémentation de barre d’état dans MFC](../../mfc/status-bar-implementation-in-mfc.md) et [Note technique 31 : les barres de contrôle](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="a-namecommandtoindexa--cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 Obtient l’index de l’indicateur pour un ID donné.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDFind`  
 ID de chaîne de l’indicateur dont l’index doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de l’indicateur en cas de réussite ; -1 en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 L’index du premier indicateur est 0.  
  
##  <a name="a-namecreatea--cstatusbarcreate"></a><a name="create"></a>CStatusBar::Create  
 Crée un état de la barre (une fenêtre enfant) et l’associe à la `CStatusBar` objet.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers le [CWnd](../../mfc/reference/cwnd-class.md) objet dont la fenêtre Windows est le parent de la barre d’état.  
  
 `dwStyle`  
 Le style de la barre d’état. Outre les fenêtres standards [styles](../../mfc/reference/window-styles.md), ces styles sont pris en charge.  
  
- `CBRS_TOP`Barre de contrôle est en haut de la fenêtre frame.  
  
- `CBRS_BOTTOM`Barre de contrôle est en bas de la fenêtre frame.  
  
- `CBRS_NOALIGN`Barre de contrôle n’est pas repositionnée lorsque le parent est redimensionné.  
  
 `nID`  
 ID de fenêtre enfant. de la barre d’outils  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Également définit la police initiale et définit l’état de la hauteur de la barre à une valeur par défaut.  
  
##  <a name="a-namecreateexa--cstatusbarcreateex"></a><a name="createex"></a>CStatusBar::CreateEx  
 Appelez cette fonction pour créer un état de la barre (une fenêtre enfant) et l’associer avec le `CStatusBar` objet.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointeur vers le [CWnd](../../mfc/reference/cwnd-class.md) objet dont la fenêtre Windows est le parent de la barre d’état.  
  
 `dwCtrlStyle`  
 Styles supplémentaires pour la création de l’élément incorporé [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) objet. La valeur par défaut spécifie une barre d’état sans une poignée de redimensionnement ou une info-bulle prennent en charge. Styles de barre d’état pris en charge sont :  
  
- **SBARS_SIZEGRIP** le contrôle de barre d’état comporte une poignée de redimensionnement à l’extrémité droite de la barre d’état. Une poignée de redimensionnement est semblable à une bordure de redimensionnement ; Il est une zone rectangulaire que l’utilisateur peut cliquer et faites glisser pour redimensionner la fenêtre parente.  
  
- **SBT_TOOLTIPS** prend en charge de la barre d’état des info-bulles.  
  
 Pour plus d’informations sur ces styles, consultez [paramètres de l’objet CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 `dwStyle`  
 Le style de barre d’état. La valeur par défaut indique qu’une barre d’état visible être créé en bas de la fenêtre frame. Appliquer n’importe quelle combinaison de styles de contrôle répertoriés dans la barre d’état [Styles de fenêtre](../../mfc/reference/window-styles.md) et [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Toutefois, ce paramètre doit toujours inclure les styles WS_CHILD et WS_VISIBLE.  
  
 `nID`  
 ID de la fenêtre la barre d’état enfant.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction définit la police initiale également et définit l’état de la hauteur de la barre à une valeur par défaut.  
  
 Utilisez `CreateEx`, au lieu de [créer](#create), lorsque certains styles doivent être présents lors de la création du contrôle barre d’état incorporée. Par exemple, définissez `dwCtrlStyle` à **SBT_TOOLTIPS** pour afficher des info-bulles dans un objet de barre d’état.  
  
##  <a name="a-namecstatusbara--cstatusbarcstatusbar"></a><a name="cstatusbar"></a>CStatusBar::CStatusBar  
 Construit un `CStatusBar` objet, crée une police de barre d’état par défaut, si nécessaire et définit les caractéristiques de police pour les valeurs par défaut.  
  
```  
CStatusBar();
```  
  
##  <a name="a-namedrawitema--cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::DrawItem  
 Cette fonction membre est appelée par l’infrastructure lorsqu’un aspect visuel d’une modification de barre d’état owner-drawn.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpDrawItemStruct`  
 Un pointeur vers un [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) structure qui contient des informations sur le type de dessin requis.  
  
### <a name="remarks"></a>Remarques  
 Le **itemAction** membre de la `DRAWITEMSTRUCT` structure définit l’action de dessin qui doit être effectuée. Remplacez cette fonction membre pour implémenter le dessin pour un mode owner-draw `CStatusBar` objet. L’application doit restaurer tous les objets interface (GDI) périphérique graphique sélectionnés pour le contexte d’affichage fournie dans `lpDrawItemStruct` avant l’arrêt de cette fonction membre.  
  
##  <a name="a-namegetitemida--cstatusbargetitemid"></a><a name="getitemid"></a>CStatusBar::GetItemID  
 Retourne l’ID de l’indicateur spécifié par `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’indicateur dont l’ID doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de l’indicateur spécifié par `nIndex`.  
  
##  <a name="a-namegetitemrecta--cstatusbargetitemrect"></a><a name="getitemrect"></a>CStatusBar::GetItemRect  
 Copie les coordonnées de l’indicateur spécifié par `nIndex` dans la structure vers laquelle pointée `lpRect`.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’indicateur de rectangle dont les coordonnées doivent être récupérés.  
  
 `lpRect`  
 Pointe vers une [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure ou un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui reçoit les coordonnées de l’indicateur spécifié par `nIndex`.  
  
### <a name="remarks"></a>Remarques  
 Coordonnées sont exprimées en pixels par rapport au coin supérieur gauche de la barre d’état.  
  
##  <a name="a-namegetpaneinfoa--cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 Jeux de `nID`, `nStyle`, et `cxWidth` à l’ID, le style et la largeur de la fenêtre de l’indicateur à l’emplacement spécifié par `nIndex`.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index du volet dont les informations sont à récupérer.  
  
 `nID`  
 Référence à un **UINT** qui est définie sur l’ID du volet.  
  
 `nStyle`  
 Référence à un **UINT** qui est défini sur le style du volet.  
  
 `cxWidth`  
 Référence à un entier qui est défini sur la largeur du volet.  
  
##  <a name="a-namegetpanestylea--cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 Appelez cette fonction membre pour récupérer le style du volet d’une barre état.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index du volet dont le style doit être récupéré.  
  
### <a name="return-value"></a>Valeur de retour  
 Le style du volet de barre d’état spécifié par `nIndex`.  
  
### <a name="remarks"></a>Remarques  
 Les style d’un volet détermine comment le volet s’affiche.  
  
 Pour obtenir la liste des styles disponibles pour les barres d’état, consultez [créer](#create).  
  
##  <a name="a-namegetpanetexta--cstatusbargetpanetext"></a><a name="getpanetext"></a>CStatusBar::GetPaneText  
 Appelez cette fonction membre pour récupérer le texte qui apparaît dans un volet de barre d’état.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  ```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be retrieved.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that contains the text to be retrieved.  
  
### Return Value  
 A `CString` object containing the pane's text.  
  
### Remarks  
 The second form of this member function fills a `CString` object with the string text.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 This member function allows direct access to the underlying common control.  
  
```  
CStatusBarCtrl se GetStatusBarCtrl() const ;  
```  
  
### Return Value  
 Contains a reference to a [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) object.  
  
### Remarks  
 Use `GetStatusBarCtrl` to take advantage of the functionality of the Windows status-bar common control, and to take advantage of the support [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) provides for status-bar customization. For example, by using the common control, you can specify a style that includes a sizing grip on the status bar, or you can specify a style to have the status bar appear at the top of the parent window's client area.  
  
 For more general information about common controls, See [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Sets each indicator's ID to the value specified by the corresponding element of the array `lpIDArray`, loads the string resource specified by each ID, and sets the indicator's text to the string.  
  
```  
BOOL SetIndicators (lpIDArray const UINT *,  
    nIDCount int) ;
```  
  
### Parameters  
 `lpIDArray`  
 Pointer to an array of IDs.  
  
 `nIDCount`  
 Number of elements in the array pointed to by `lpIDArray`.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Sets the specified indicator pane to a new ID, style, and width.  
  
```  
void SetPaneInfo (int nIndex,  
    UINT nID,  
    UINT nStyle,  
    cxWidth int) ;
```  
  
### Parameters  
 `nIndex`  
 Index of the indicator pane whose style is to be set.  
  
 `nID`  
 New ID for the indicator pane.  
  
 `nStyle`  
 New style for the indicator pane.  
  
 `cxWidth`  
 New width for the indicator pane.  
  
### Remarks  
 The following indicator styles are supported:  
  
- **SBPS_NOBORDERS** No 3-D border around the pane.  
  
- **SBPS_POPOUT** Reverse border so that text "pops out."  
  
- **SBPS_DISABLED** Do not draw text.  
  
- **SBPS_STRETCH** Stretch pane to fill unused space. Only one pane per status bar can have this style.  
  
- **SBPS_NORMAL** No stretch, borders, or pop-out.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Call this member function to set the style of a status bar's pane.  
  
```  
void SetPaneStyle (int nIndex,  
    UINT nStyle) ;
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose style is to be set.  
  
 `nStyle`  
 Style of the pane whose style is to be set.  
  
### Remarks  
 A pane's style determines how the pane appears.  
  
 For a list of styles available for status bars, see [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Call this member function to set the pane text to the string pointed to by `lpszNewText`.  
  
```  
BOOL SetPaneText (int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE) ;
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be set.  
  
 `lpszNewText`  
 Pointer to the new pane text.  
  
 *bUpdate*  
 If **TRUE**, the pane is invalidated after the text is set.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 After you call `SetPaneText`, you must add a UI update handler to display the new text in the status bar.  
  
### Example  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## See Also  
 [MFC Sample CTRLBARS](../../visual-cpp-samples.md)   
 [MFC Sample DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)

