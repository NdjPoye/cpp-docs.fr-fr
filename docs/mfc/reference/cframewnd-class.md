---
title: CFrameWnd (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- frame window classes, base class
- single document interface (SDI), frame windows
- frame windows, creating
- CFrameWnd class
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
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
ms.openlocfilehash: a8df28ed10208973832476b68140594c206bc22b
ms.lasthandoff: 02/24/2017

---
# <a name="cframewnd-class"></a>CFrameWnd (classe)
Fournit les fonctionnalités d'une fenêtre frame contextuelle ou superposée d'interface monodocument (SDI) Windows, ainsi que des membres permettant de gérer la fenêtre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|Construit un objet `CFrameWnd`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|Rend l’image visible et accessible à l’utilisateur.|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|Définit la fenêtre frame modal.|  
|[CFrameWnd::Create](#create)|L’appel pour créer et initialiser la fenêtre frame Windows associée à la `CFrameWnd` objet.|  
|[CFrameWnd::CreateView](#createview)|Crée une vue dans un intervalle qui n’est pas dérivé `CView`.|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|Ancre une barre de contrôle.|  
|[CFrameWnd::EnableDocking](#enabledocking)|Permet à une barre de contrôle ancré.|  
|[CFrameWnd::EndModalState](#endmodalstate)|Met fin à l’état de la fenêtre frame modal. Permet à toutes les fenêtres désactivées par `BeginModalState`.|  
|[CFrameWnd::FloatControlBar](#floatcontrolbar)|Flotte à une barre de contrôle.|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|Retourne l’actif **CDocument** objet.|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|Retourne l’actif `CFrameWnd` objet.|  
|[CFrameWnd::GetActiveView](#getactiveview)|Retourne l’actif `CView` objet.|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|Récupère la barre de contrôle.|  
|[CFrameWnd::GetDockState](#getdockstate)|Récupère l’état d’ancrage d’une fenêtre frame.|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|Récupère l’état d’affichage du menu de l’application MFC en cours.|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|Indique si le comportement par défaut du menu de l’application MFC en cours est masquée ou visible.|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|Retourne un pointeur vers l’état de la barre appartenant à la fenêtre frame.|  
|[CFrameWnd::GetMessageString](#getmessagestring)|Récupère le message correspondant à un ID de commande.|  
|[CFrameWnd::GetTitle](#gettitle)|Récupère le titre de la barre de contrôles connexes.|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|Provoque la `OnInitialUpdate` fonction membre appartenant à toutes les vues dans la fenêtre frame à appeler.|  
|[CFrameWnd::InModalState](#inmodalstate)|Retourne une valeur indiquant si une fenêtre frame est dans un état modal.|  
|[CFrameWnd::IsTracking](#istracking)|Détermine si la barre de fractionnement est actuellement déplacée.|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|Appel pour charger une table d’accélérateurs.|  
|[CFrameWnd::LoadBarState](#loadbarstate)|L’appel à restaurer les paramètres de barre de contrôle.|  
|[CFrameWnd::LoadFrame](#loadframe)|L’appel à créer dynamiquement une fenêtre frame d’informations sur la ressource.|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|Négocie l’espace de bordure de la fenêtre frame.|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|Appelé chaque fois qu’une action est effectuée sur la barre de contrôle spécifié.|  
|[CFrameWnd::OnContextHelp](#oncontexthelp)|Gère MAJ + F1 Aide pour les éléments en place.|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|Définit la fenêtre frame principale de l’application dans et hors mode Aperçu avant impression.|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|Appelé par l’infrastructure lorsque le menu associé est mis à jour.|  
|[CFrameWnd::RecalcLayout](#recalclayout)|Repositionne les barres de contrôle de la `CFrameWnd` objet.|  
|[CFrameWnd::SaveBarState](#savebarstate)|L’appel à enregistrer les paramètres de barre de contrôle.|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|Désigne la vue spécifiée à la vue active pour l’aperçu riche.|  
|[CFrameWnd::SetActiveView](#setactiveview)|Définit l’actif `CView` objet.|  
|[CFrameWnd::SetDockState](#setdockstate)|Appel pour ancrer la fenêtre frame dans la fenêtre principale.|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|Définit l’état d’affichage du menu de l’application MFC actuelle masqués ou affichés.|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|Définit le comportement par défaut du menu de l’application MFC actuelle pour être masquées ou visibles.|  
|[CFrameWnd::SetMessageText](#setmessagetext)|Définit le texte de la barre d’état standard.|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|Définit la position actuelle pour la barre de progression affichée sur la barre des tâches de Windows 7.|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|Définit la plage de la barre de progression affichée sur la barre des tâches de Windows 7.|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|Définit le type et l’état de l’indicateur de progression affichée sur un bouton de barre des tâches.|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|Surchargé. S’applique à un segment de recouvrement à un bouton de barre des tâches pour indiquer l’état de l’application ou d’une notification à l’utilisateur.|  
|[CFrameWnd::SetTitle](#settitle)|Définit le titre de la barre de contrôles connexes.|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|L’appel à afficher la barre de contrôle.|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|Affiche toutes les fenêtres qui sont des descendants de le `CFrameWnd` objet.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|Crée une fenêtre du client pour la trame.|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|Appelé avant que le menu de l’application MFC en cours est masqué.|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|Appelé avant que le menu de l’application MFC en cours s’affiche.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|Contrôles automatique activent et désactiver les fonctionnalités des éléments de menu.|  
|[CFrameWnd::rectDefault](#rectdefault)|Passer ce statique `CRect` en tant que paramètre lorsque vous créez un `CFrameWnd` objet pour permettre à Windows de choisir la taille initiale et la position de la fenêtre.|  
  
## <a name="remarks"></a>Notes  
 Pour créer une fenêtre frame utiles pour votre application, dérivez une classe de `CFrameWnd`. Ajoutez des variables membres à la classe dérivée pour stocker les données spécifiques à votre application. Implémentez des fonctions membres de gestionnaire de messages et une table des messages dans la classe dérivée pour préciser ce qu'il advient quand des messages sont dirigés vers la fenêtre.  
  
 Il existe trois manières de construire une fenêtre frame :  
  
-   Construire directement à l’aide de [créer](#create).  
  
-   Construire directement à l’aide de [LoadFrame](#loadframe).  
  
-   Indirectement construire à l’aide d’un modèle de document.  
  
 Avant d’appeler une **créer** ou `LoadFrame`, vous devez créer l’objet de fenêtre frame sur le segment de mémoire à l’aide de C++ **nouveau** opérateur. Avant d’appeler **créer**, vous pouvez également enregistrer une classe de fenêtre avec la [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) fonction globale pour définir les styles d’icône et de la classe de l’image.  
  
 Utilisez le **créer** fonction membre pour passer des paramètres de création du frame immédiates comme arguments.  
  
 `LoadFrame`nécessite moins d’arguments que **créer**et extrait à la place la plupart de ses valeurs par défaut de ressources, y compris la légende du frame, icône, table d’accélérateurs et menu. Pour être accessible par `LoadFrame`, toutes ces ressources doivent avoir le même ID de ressource (par exemple, **IDR_MAINFRAME**).  
  
 Lorsqu’un `CFrameWnd` objet contient des affichages et des documents, elles sont créées indirectement par le framework plutôt que directement par le programmeur. Le `CDocTemplate` objet orchestre la création de l’image, la création des vues contenant et la connexion de l’affichage pour le document approprié. Les paramètres de la `CDocTemplate` constructeur spécifie le `CRuntimeClass` des trois classes impliquées (document, image et affichage). Un `CRuntimeClass` objet est utilisé par l’infrastructure pour créer dynamiquement des nouvelles images spécifiées par l’utilisateur (par exemple, en utilisant la commande fichier nouveau ou la commande nouvelle fenêtre de plusieurs documents MDI (interface)).  
  
 Une classe de fenêtre frame dérivée de `CFrameWnd` doit être déclaré avec `DECLARE_DYNCREATE` afin que les éléments ci-dessus `RUNTIME_CLASS` mécanisme fonctionne correctement.  
  
 Un `CFrameWnd` contient les implémentations par défaut pour exécuter les fonctions suivantes de la fenêtre principale dans une application pour Windows :  
  
-   Un `CFrameWnd` fenêtre frame conserve une trace d’une vue active est indépendante de la fenêtre active de Windows ou le focus d’entrée actuel. Lorsque le frame est réactivé, la vue active est avertie en appelant `CView::OnActivateView`.  
  
-   Commande de messages et nombreux messages de notification de frame courants, y compris celles gérées par le `OnSetFocus`, `OnHScroll`, et `OnVScroll` fonctions de `CWnd`, sont déléguées à un `CFrameWnd` fenêtre frame dans la vue actuellement active.  
  
-   La vue actuellement active (ou fenêtre de frame MDI enfant active dans le cas d’un frame MDI) peut déterminer la légende de la fenêtre frame. Cette fonctionnalité peut être désactivée en désactivant la **FWS_ADDTOTITLE** bit de style de la fenêtre frame.  
  
-   Un `CFrameWnd` fenêtre frame gère la position des barres de contrôles, des vues et autres fenêtres enfants dans la zone cliente de la fenêtre frame. Une fenêtre frame effectue également la mise à jour des temps d’inactivité de la barre d’outils et autres boutons de barre de contrôle. Un `CFrameWnd` fenêtre frame possède également des implémentations par défaut des commandes pour activer et désactiver la barre d’outils et barre d’état.  
  
-   Un `CFrameWnd` fenêtre frame gère la barre de menus principale. Lorsqu’un menu contextuel s’affiche, la fenêtre frame utilise le **UPDATE_COMMAND_UI** mécanisme pour déterminer les éléments de menu doivent être activés, désactivés ou activés. Lorsque l’utilisateur sélectionne un élément de menu, la fenêtre frame met à jour la barre d’état avec la chaîne de message pour cette commande.  
  
-   Un `CFrameWnd` fenêtre frame possède une table d’accélérateurs facultative qui convertit automatiquement les accélérateurs clavier.  
  
-   A `CFrameWnd` fenêtre frame comporte un ID d’aide facultatif défini avec `LoadFrame` qui est utilisé pour l’aide contextuelle. Une fenêtre frame est le principal orchestrator des États semi-modaux tels que l’aide contextuelle (MAJ + F1) et les modes d’aperçu avant impression.  
  
-   Un `CFrameWnd` fenêtre frame ouvre un fichier à partir du Gestionnaire de fichier de glisser -déplacer dans la fenêtre frame. Si une extension de fichier est enregistrée et associée à l’application, la fenêtre frame répond à la demande d’ouverture dynamic data exchange (DDE) qui se produit lorsque l’utilisateur ouvre un fichier de données dans le Gestionnaire de fichiers ou le **ShellExecute** Windows fonction est appelée.  
  
-   Si la fenêtre frame est la fenêtre principale de l’application (autrement dit, `CWinThread::m_pMainWnd`), lorsque l’utilisateur ferme l’application, la fenêtre frame invite l’utilisateur à enregistrer les documents modifiés (pour `OnClose` et `OnQueryEndSession`).  
  
-   Si la fenêtre frame est la fenêtre principale de l’application, la fenêtre frame est le contexte d’exécution WinHelp. Fermeture de la fenêtre frame s’arrêtera WINHELP. EXE s’il a été lancé pour l’aide de cette application.  
  
 N’utilisez pas le C++ **supprimer** opérateur pour détruire une fenêtre frame. Utilisez plutôt `CWnd::DestroyWindow` . Le `CFrameWnd` implémentation de `PostNcDestroy` supprime l’objet C++ lorsque la fenêtre est détruite. Lorsque l’utilisateur ferme la fenêtre frame, la valeur par défaut `OnClose` gestionnaire appelle `DestroyWindow`.  
  
 Pour plus d’informations sur `CFrameWnd`, consultez [fenêtres Frame](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameactivateframea--cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::ActivateFrame  
 Appelez cette fonction membre pour activer et restaure la fenêtre frame, afin qu’il soit visible et accessible à l’utilisateur.  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCmdShow`  
 Spécifie le paramètre à passer au [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). Par défaut, l’image est indiquée et restaurée correctement.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est généralement appelée après un événement d’interface non-utilisateur comme DDE, OLE ou autres événements qui peuvent afficher la fenêtre frame ou son contenu à l’utilisateur.  
  
 L’implémentation par défaut active le frame amène au haut de l’ordre de plan et si nécessaire, exécute la procédure de fenêtre frame principale de l’application.  
  
 Remplacez cette fonction membre pour modifier comment une image est activée. Par exemple, vous pouvez forcer des fenêtres MDI enfants à être agrandi. Ajoutez la fonctionnalité appropriée, puis appeler la version classe de base avec explicite `nCmdShow`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing n °&1;](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 Appelez cette fonction membre pour rendre modale une fenêtre frame.  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namecframewnda--cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 Construit un `CFrameWnd` de l’objet, mais ne crée pas de la fenêtre frame visible.  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Remarques  
 Appelez **créer** pour créer la fenêtre visible.  
  
##  <a name="a-namecreatea--cframewndcreate"></a><a name="create"></a>CFrameWnd::Create  
 L’appel pour créer et initialiser la fenêtre frame Windows associée à la `CFrameWnd` objet.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CWnd* pParentWnd = NULL,  
    LPCTSTR lpszMenuName = NULL,  
    DWORD dwExStyle = 0,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszClassName`  
 Pointe vers une chaîne de caractères se terminant par null qui nomme la classe Windows. Le nom de classe peut être n’importe quel nom inscrit avec le `AfxRegisterWndClass` fonction globale ou **RegisterClass** fonction Windows. Si **NULL**, utilise la valeur par défaut prédéfinie `CFrameWnd` attributs.  
  
 `lpszWindowName`  
 Pointe vers une chaîne de caractères terminée par le caractère null qui représente le nom de la fenêtre. Utilisé comme texte de la barre de titre.  
  
 `dwStyle`  
 Spécifie la fenêtre [style](../../mfc/reference/window-styles.md) attributs. Inclure les **FWS_ADDTOTITLE** style si vous souhaitez que la barre de titre pour afficher automatiquement le nom du document représenté dans la fenêtre.  
  
 `rect`  
 Spécifie la taille et la position de la fenêtre. Le `rectDefault` valeur permet à Windows spécifier la taille et la position de la nouvelle fenêtre.  
  
 `pParentWnd`  
 Spécifie la fenêtre parente de la fenêtre frame. Ce paramètre doit être **NULL** pour les fenêtres frames de niveau supérieur.  
  
 *lpszMenuName*  
 Identifie le nom de la ressource de menu à utiliser avec la fenêtre. Utilisez **MAKEINTRESOURCE** si le menu contient un ID d’entier au lieu d’une chaîne. Ce paramètre peut être **NULL**.  
  
 `dwExStyle`  
 Spécifie la fenêtre étendue [style](../../mfc/reference/extended-window-styles.md) attributs.  
  
 `pContext`  
 Spécifie un pointeur vers un [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure. Ce paramètre peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation aboutit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Construire un `CFrameWnd` objet en deux étapes. Tout d’abord, appeler le constructeur, qui construit la `CFrameWnd` de l’objet, puis appelez **créer**, qui crée la fenêtre frame Windows et l’attache à le `CFrameWnd` objet. **Créer** initialise le nom de classe et le nom de la fenêtre de la fenêtre et enregistre les valeurs par défaut pour son style, le parent et le menu associé.  
  
 Utilisez `LoadFrame` plutôt que **créer** pour charger la fenêtre frame d’une ressource au lieu de spécifier ses arguments.  
  
##  <a name="a-namecreateviewa--cframewndcreateview"></a><a name="createview"></a>CFrameWnd::CreateView  
 Appelez `CreateView` pour créer un affichage dans un frame.  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>Paramètres  
 `pContext`  
 Spécifie le type de document et de vue.  
  
 `nID`  
 Numéro d’identification d’une vue.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un `CWnd` objet en cas de réussite ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction membre pour créer « vues » qui ne sont pas `CView`-dérivée dans un frame. Après avoir appelé `CreateView`, vous devez manuellement définissez l’affichage actif et qu’il soit visible ; ces tâches ne sont pas effectuées automatiquement par `CreateView`.  
  
##  <a name="a-namedockcontrolbara--cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 Provoque une barre de contrôle ancré à la fenêtre frame.  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBar`  
 Pointe vers la barre de contrôle pour être ancré.  
  
 `nDockBarID`  
 Détermine quel côté de la fenêtre frame à prendre en compte pour l’ancrage. Il peut être 0, ou un ou plusieurs des opérations suivantes :  
  
- `AFX_IDW_DOCKBAR_TOP`Ancrer en haut de la fenêtre frame.  
  
- **AFX_IDW_DOCKBAR_BOTTOM** ancrer à la partie inférieure de la fenêtre frame.  
  
- `AFX_IDW_DOCKBAR_LEFT`Ancrer sur le côté gauche de la fenêtre frame.  
  
- `AFX_IDW_DOCKBAR_RIGHT`Ancrer à droite de la fenêtre frame.  
  
 La valeur 0, la barre de contrôle peut être ancrée à n’importe quel côté activée pour l’ancrage de la fenêtre frame de destination.  
  
 `lpRect`  
 Détermine, en coordonnées d’écran, où la barre de contrôle sera ancrée dans la zone non cliente de la fenêtre frame de destination.  
  
### <a name="remarks"></a>Remarques  
 La barre de contrôle sera ancrée à l’un des côtés de la fenêtre frame spécifié dans les appels à la fois aux [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) et [CFrameWnd::EnableDocking](#enabledocking). Le côté choisi est déterminé par `nDockBarID`.  
  
##  <a name="a-nameenabledockinga--cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::EnableDocking  
 Appelez cette fonction pour activer les barres de contrôle ancrable dans une fenêtre frame.  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwDockStyle`  
 Spécifie les côtés de la fenêtre frame peuvent servir de station d’accueil de sites pour les barres de contrôles. Il peut être une ou plusieurs des opérations suivantes :  
  
- `CBRS_ALIGN_TOP`Permet d’ancrage en haut de la zone cliente.  
  
- `CBRS_ALIGN_BOTTOM`Permet d’ancrage en bas de la zone cliente.  
  
- `CBRS_ALIGN_LEFT`Permet d’ancrage sur le côté gauche de la zone cliente.  
  
- `CBRS_ALIGN_RIGHT`Permet d’ancrage située à droite de la zone cliente.  
  
- `CBRS_ALIGN_ANY`Autorise la fixation sur n’importe quel côté de la zone cliente.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, les barres de contrôle seront ancrés à un côté de la fenêtre frame dans l’ordre suivant : haut, bas, gauche, droite.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CToolBar::Create](../../mfc/reference/ctoolbar-class.md#create).  
  
##  <a name="a-nameendmodalstatea--cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::EndModalState  
 Appelez cette fonction membre pour changer une fenêtre frame modale en fenêtre frame non modale.  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Notes  
 `EndModalState`permet à toutes les fenêtres désactivées par [BeginModalState](#beginmodalstate).  
  
##  <a name="a-namefloatcontrolbara--cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd::FloatControlBar  
 Appelez cette fonction pour provoquer une barre de contrôle n’est ancré à la fenêtre frame.  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBar`  
 Pointe vers la barre de contrôle à flotter.  
  
 `point`  
 L’emplacement, en coordonnées d’écran, où le coin supérieur gauche de la barre de contrôle est placé.  
  
 `dwStyle`  
 Spécifie s’il faut aligner la barre de contrôle horizontalement ou verticalement dans sa fenêtre frame. Il peut être l’une des opérations suivantes :  
  
- `CBRS_ALIGN_TOP`Oriente la barre de contrôle verticalement.  
  
- `CBRS_ALIGN_BOTTOM`Oriente la barre de contrôle verticalement.  
  
- `CBRS_ALIGN_LEFT`Oriente la barre de contrôle horizontalement.  
  
- `CBRS_ALIGN_RIGHT`Oriente la barre de contrôle horizontalement.  
  
 Si les styles sont passés en spécifiant l’orientation horizontale et verticale, la barre d’outils sera orienté horizontalement.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, cela au démarrage de l’application lorsque le programme de restauration des paramètres à partir de l’exécution précédente.  
  
 Cette fonction est appelée par l’infrastructure lorsque l’utilisateur provoque une opération déplacer en relâchant le bouton de gauche de la souris tout en faisant glisser la barre de contrôle sur un emplacement qui n’est pas disponible pour la station d’accueil.  
  
##  <a name="a-namegetactivedocumenta--cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 Appelez cette fonction membre pour obtenir un pointeur vers la version **CDocument** associé à la vue active actuelle.  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la version [CDocument](../../mfc/reference/cdocument-class.md). S’il n’existe aucun document actuel, retourne **NULL**.  
  
##  <a name="a-namegetactiveframea--cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 Appelez cette fonction membre pour obtenir un pointeur vers l’actif fenêtre interface multidocument (MDI) enfant d’une fenêtre frame MDI.  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre MDI enfant active. Si l’application est une application SDI, ou la fenêtre frame MDI ne possède aucun document actif, implicite **cela** pointeur sera retourné.  
  
### <a name="remarks"></a>Notes  
 Si aucun enfant MDI actif ou l’application est une interface monodocument (SDI), implicite **cela** pointeur est retourné.  
  
##  <a name="a-namegetactiveviewa--cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView  
 Appelez cette fonction membre pour obtenir un pointeur vers la vue active (le cas échéant) associé à une fenêtre frame ( `CFrameWnd`).  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la version [CView](../../mfc/reference/cview-class.md). S’il n’existe aucun affichage actuel, retourne **NULL**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction retourne **NULL** lorsqu’elle est appelée pour une fenêtre frame principale MDI ( `CMDIFrameWnd`). Dans une application MDI, la fenêtre frame principale MDI n’a pas une vue associée. Au lieu de cela, chaque fenêtre enfant ( `CMDIChildWnd`) a une ou plusieurs vues associées. La vue active dans une application MDI peut être obtenue par la recherche tout d’abord la fenêtre MDI enfant active et la détection de la vue active de cette fenêtre enfant. Vous trouverez la fenêtre MDI enfant active en appelant la fonction `MDIGetActive` ou **GetActiveFrame** comme illustré dans le code suivant :  
  
 [!code-cpp[NVC_MFCWindowing n °&2;](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="a-namegetcontrolbara--cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 Appelez `GetControlBar` pour accéder à la barre de contrôle qui est associée avec le code.  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Numéro d’identification d’une barre de contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la barre de contrôle qui est associé avec le code.  
  
### <a name="remarks"></a>Remarques  
 Le `nID` paramètre fait référence à l’identificateur unique passé à la **créer** méthode de la barre de contrôle. Pour plus d’informations sur les barres de contrôles, reportez-vous à la rubrique intitulée [les barres de contrôle](../../mfc/control-bars.md).  
  
 `GetControlBar`Renvoie la barre de contrôle même s’il est flottant et par conséquent n’est pas une fenêtre enfant du cadre.  
  
##  <a name="a-namegetdockstatea--cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState  
 Appelez cette fonction membre pour stocker les informations d’état à propos des barres de contrôle de la fenêtre frame dans un `CDockState` objet.  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `state`  
 Contient l’état actuel de la fenêtre frame barres de contrôle au moment du retour.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez ensuite écrire le contenu de `CDockState` à l’utilisation de stockage `CDockState::SaveState` ou `Serialize`. Si vous souhaitez ultérieurement restaurer les barres de contrôles à un état antérieur, charger l’état avec `CDockState::LoadState` ou `Serialize`, puis appelez `SetDockState` pour appliquer l’état précédent aux barres de contrôles de la fenêtre frame.  
  
##  <a name="a-namegetmenubarstatea--cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 Récupère l’état d’affichage du menu de l’application MFC en cours.  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour peut avoir les valeurs suivantes :  
  
-   AFX_MBS_VISIBLE (0 x&01;) – le menu est visible.  
  
-   AFX_MBS_HIDDEN (0 x&02;) – le menu est masqué.  
  
### <a name="remarks"></a>Remarques  
 Si une erreur d’exécution se produit, cette méthode déclare en mode débogage et déclenche une exception dérivée de le [CException](../../mfc/reference/cexception-class.md) classe.  
  
##  <a name="a-namegetmenubarvisibilitya--cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 Indique si l’état par défaut du menu de l’application MFC en cours est visible ou masquée.  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne une des valeurs suivantes :  
  
-   AFX_MBV_KEEPVISIBLE (0 x&01;) - le menu est affiché et par défaut n’est pas activé.  
  
-   AFX_MBV_DISPLAYONFOCUS (0 x&02;) - le menu est masqué par défaut. Si le menu est masqué, appuyez sur la touche ALT pour afficher le menu et lui donner le focus. Si le menu s’affiche, appuyez sur la touche ALT ou sur ÉCHAP pour la masquer.  
  
-   AFX_MBV_ DISPLAYONFOCUS (0 X&02;) | AFX_MBV_DISPLAYONF10 (0 x&04;) (combinaison de bits (OR)) - le menu est masqué par défaut. Si le menu est masqué, appuyez sur la touche F10 pour afficher le menu et lui donner le focus. Si le menu s’affiche, appuyez sur la touche F10 pour basculer le focus sur ou hors du menu. Le menu s’affiche jusqu'à ce que vous appuyez sur la touche ALT ou sur ÉCHAP pour la masquer.  
  
### <a name="remarks"></a>Notes  
 Si une erreur d’exécution se produit, cette méthode déclare en mode débogage et déclenche une exception dérivée de le [CException](../../mfc/reference/cexception-class.md) classe.  
  
##  <a name="a-namegetmessagebara--cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 Appelez cette fonction membre pour obtenir un pointeur vers la barre d’état.  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre de la barre d’état.  
  
##  <a name="a-namegetmessagestringa--cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 Remplacez cette fonction pour fournir des chaînes personnalisées pour l’ID de commande.  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID de ressource du message souhaité.  
  
 `rMessage`  
 `CString`objet dans lequel placer le message.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut charge simplement la chaîne spécifiée par `nID` du fichier de ressources. Cette fonction est appelée par l’infrastructure lorsque la chaîne du message dans la barre d’état doit mettre à jour.  
  
##  <a name="a-namegettitlea--cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle  
 Récupère le titre de l’objet window.  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant le titre de l’objet de fenêtre en cours.  
  
##  <a name="a-nameinitialupdateframea--cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 Appelez **IntitialUpdateFrame** après la création d’un nouveau bloc avec **créer**.  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDoc`  
 Pointe vers le document auquel la fenêtre frame est associée. Peut être **NULL**.  
  
 `bMakeVisible`  
 Si **TRUE**, indique que le frame doit devenir visible et actif. Si **FALSE**, aucuns descendants ne sont visibles.  
  
### <a name="remarks"></a>Remarques  
 Alors tous les affichages dans cette fenêtre frame pour recevoir leur `OnInitialUpdate` appels.  
  
 En outre, s’il n’est pas une vue active, l’affichage de la fenêtre frame principale devient actif. La vue principale est une vue avec l’ID enfant de **AFX_IDW_PANE_FIRST**. Enfin, la fenêtre frame est rendue visible si `bMakeVisible` est différente de zéro. Si `bMakeVisible` est 0, le focus actuel et l’état visible de la fenêtre frame demeurent inchangés. Il n’est pas nécessaire d’appeler cette fonction lorsque vous utilisez l’implémentation de l’infrastructure du nouveau fichier et ouvrir le fichier.  
  
##  <a name="a-nameinmodalstatea--cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::InModalState  
 Appelez cette fonction membre pour vérifier si une fenêtre frame est modale ou non modale.  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si Oui ; sinon 0.  
  
##  <a name="a-nameistrackinga--cframewndistracking"></a><a name="istracking"></a>CFrameWnd::IsTracking  
 Appelez cette fonction membre pour déterminer si la barre de fractionnement de la fenêtre est actuellement déplacée.  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si une opération de fractionnement est en cours ; sinon 0.  
  
##  <a name="a-nameloadacceltablea--cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 Appel pour charger la table d’accélérateurs spécifié.  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResourceName`  
 Identifie le nom de la ressource de l’accélérateur. Utilisez **MAKEINTRESOURCE** si la ressource est identifiée par un ID d’entier.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la table d’accélérateurs a été chargée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Une seule table peut être chargée à la fois.  
  
 Tables d’accélérateurs chargées depuis les ressources sont libérées automatiquement lorsque l’application s’arrête.  
  
 Si vous appelez `LoadFrame` pour créer la fenêtre frame, le framework charge une table d’accélérateurs, les ressources de menu et icône et un appel ultérieur à cette fonction membre est alors inutile.  
  
##  <a name="a-nameloadbarstatea--cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 Appelez cette fonction pour restaurer les paramètres de chaque barre de contrôles appartenant à la fenêtre frame.  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszProfileName`  
 Nom d’une section dans le fichier d’initialisation (INI) ou une clé dans le Registre Windows où sont stockées les informations d’état.  
  
### <a name="remarks"></a>Remarques  
 Informations restaurées incluent la visibilité, l’orientation horizontal/vertical, état d’ancrage et la position de la barre de contrôle.  
  
 Les paramètres que vous souhaitez restaurer doivent être écrites dans le Registre avant d’appeler `LoadBarState`. Écrire les informations dans le Registre en appelant [CWinApp::SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey). Écrire les informations dans le fichier INI en appelant [SaveBarState](#savebarstate).  
  
##  <a name="a-nameloadframea--cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd::LoadFrame  
 L’appel à créer dynamiquement une fenêtre frame d’informations sur la ressource.  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDResource`  
 ID de ressources partagées associées à la fenêtre frame.  
  
 *dwDefaultStyle*  
 L’image [style](../../mfc/reference/window-styles.md). Inclure les **FWS_ADDTOTITLE** style si vous souhaitez que la barre de titre pour afficher automatiquement le nom du document représenté dans la fenêtre.  
  
 `pParentWnd`  
 Pointeur vers le parent du cadre.  
  
 `pContext`  
 Un pointeur vers un [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure. Ce paramètre peut être **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Construire un `CFrameWnd` objet en deux étapes. Tout d’abord, appeler le constructeur, qui construit la `CFrameWnd` de l’objet, puis appelez `LoadFrame`, qui charge les fenêtres de frame et les ressources associées et attache la fenêtre frame le `CFrameWnd` objet. Le `nIDResource` paramètre spécifie le menu, la table d’accélérateurs, l’icône et la ressource de chaîne du titre de la fenêtre frame.  
  
 Utilisez le **créer** fonction membre plutôt que `LoadFrame` lorsque vous souhaitez spécifier tous les paramètres de création de la fenêtre frame.  
  
 Le framework appelle `LoadFrame` lorsqu’il crée une fenêtre frame à l’aide d’un objet de modèle de document.  
  
 L’infrastructure utilise le `pContext` argument pour spécifier les objets pour la connexion à la fenêtre frame, y compris tous les objets de vue contenus. Vous pouvez définir le `pContext` l’argument de **NULL** lorsque vous appelez `LoadFrame`.  
  
##  <a name="a-namembautomenuenablea--cframewndmbautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 Lorsque ce membre de données est activé (qui est la valeur par défaut), les éléments de menu qui n’ont pas `ON_UPDATE_COMMAND_UI` ou `ON_COMMAND` gestionnaires seront automatiquement désactivées lorsque l’utilisateur retire un menu déroulant.  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Remarques  
 Les éléments de menu ont une `ON_COMMAND` Gestionnaire mais aucune `ON_UPDATE_COMMAND_UI` gestionnaire sera activé automatiquement.  
  
 Lorsque ce membre de données est défini, les éléments de menu sont automatiquement activés de la même façon que les boutons de barre d’outils sont activés.  
  
> [!NOTE]
> `m_bAutoMenuEnable`n’a aucun effet sur les éléments de menu de niveau supérieur.  
  
 Ce membre de données simplifie l’implémentation de commandes facultatives en fonction de la sélection actuelle et réduit le besoin d’écrire `ON_UPDATE_COMMAND_UI` gestionnaires pour activer et désactiver des éléments de menu.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing n °&3;](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="a-namenegotiateborderspacea--cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 Appelez cette fonction membre pour négocier espace bordure dans une fenêtre frame lors de l’activation d’inplace OLE.  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>Paramètres  
 *nBorderCmd*  
 Contient l’une des valeurs suivantes à partir de la **enum BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** = 3  
  
 `lpRectBorder`  
 Pointeur vers un [RECT](../../mfc/reference/rect-structure1.md) structure ou un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui spécifie les coordonnées de la bordure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est la **CFrameWnd** mise en œuvre de la négociation d’espace OLE bordure.  
  
##  <a name="a-nameonbarchecka--cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 Appelé chaque fois qu’une action est effectuée sur la barre de contrôle spécifié.  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’ID du contrôle de la barre est affichée.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la barre de contrôle existant ; sinon 0.  
  
##  <a name="a-nameoncontexthelpa--cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd::OnContextHelp  
 Gère MAJ + F1 Aide pour les éléments en place.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Remarques  
 Pour activer l’aide contextuelle, vous devez ajouter une  
  
 [!code-cpp[NVC_MFCDocViewSDI&#16;](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 l’instruction à votre `CFrameWnd` classe table des messages et ajouter une entrée de table d’accélérateurs, généralement MAJ + F1, pour activer cette fonction membre.  
  
 Si votre application est un conteneur OLE, `OnContextHelp` place tous les éléments en place contenus dans l’objet de fenêtre frame en mode d’aide. Le curseur se transforme en flèche et un point d’interrogation et que l’utilisateur peut déplacer le pointeur de la souris, puis appuyez sur le bouton gauche de la souris pour sélectionner une boîte de dialogue, une fenêtre, un menu ou un bouton de commande. Cette fonction membre appelle la fonction Windows `WinHelp` avec le contexte d’aide de l’objet sous le curseur.  
  
##  <a name="a-nameoncreateclienta--cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 Appelé par l’infrastructure pendant l’exécution de `OnCreate`.  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpcs`  
 Un pointeur vers un Windows [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) structure *.*  
  
 `pContext`  
 Un pointeur vers un [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) structure *.*  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Jamais appeler cette fonction.  
  
 L’implémentation par défaut de cette fonction crée un `CView` objet à partir des informations fournies dans `pContext`, si possible.  
  
 Remplacez cette fonction pour remplacer les valeurs passées dans la `CCreateContext` de l’objet ou pour modifier les façon dont les contrôles dans la zone principale du client de la fenêtre frame sont créés. Le `CCreateContext` vous pouvez substituer les membres décrits dans le [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) (classe).  
  
> [!NOTE]
>  Ne remplacez pas les valeurs passées dans la `CREATESTRUCT` structure. Ils sont uniquement à titre d’information. Si vous souhaitez remplacer le rectangle de la première fenêtre, par exemple, remplacer le `CWnd` fonction membre [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).  
  
##  <a name="a-nameonhidemenubara--cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 Cette fonction est appelée lorsque le système est sur le point de masquer la barre de menus dans l’application MFC en cours.  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Remarques  
 Ce gestionnaire d’événements permet à votre application effectuer des actions personnalisées lorsque le système est sur le point de masquer le menu. Vous ne pouvez pas empêcher le menu de masquer, mais vous pouvez, par exemple, appeler des autres méthodes permettant de récupérer le style de menu ou d’un état.  
  
##  <a name="a-nameonsetpreviewmodea--cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 Appelez cette fonction membre pour définir la fenêtre frame principale de l’application dans et en dehors du mode Aperçu avant impression.  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Paramètres  
 *bPreview*  
 Spécifie s’il faut placer l’application en mode d’aperçu avant impression. La valeur **TRUE** à placer dans l’aperçu avant impression, **FALSE** pour annuler le mode Aperçu.  
  
 `pState`  
 Un pointeur vers un **CPrintPreviewState** structure.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut désactive toutes les barres d’outils standard et masque le menu principal et la fenêtre principale du client. Cette commande active les fenêtres frames MDI dans des fenêtres de frame SDI temporaires.  
  
 Remplacez cette fonction membre pour personnaliser le masquage et l’affichage des barres de contrôles et d’autres parties de la fenêtre frame pendant l’aperçu avant impression. Appeler l’implémentation de classe de base à partir de dans la version substituée.  
  
##  <a name="a-nameonshowmenubara--cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 Cette fonction est appelée lorsque le système est sur le point d’afficher la barre de menus dans l’application MFC en cours.  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Remarques  
 Ce gestionnaire d’événements permet à votre application effectuer des actions personnalisées lorsque le menu est sur le point d’être affiché. Vous ne pouvez pas empêcher le menu Affichage, mais vous pouvez, par exemple, appeler des autres méthodes permettant de récupérer le style de menu ou d’un état.  
  
##  <a name="a-nameonupdatecontrolbarmenua--cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 Appelé par l’infrastructure lorsque le menu associé est mis à jour.  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un [CCmdUI](../../mfc/reference/ccmdui-class.md) objet qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la [activer](../../mfc/reference/ccmdui-class.md#enable) fonction membre de la `CCmdUI` par le biais de l’objet `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
##  <a name="a-namerecalclayouta--cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd::RecalcLayout  
 Appelé par l’infrastructure lorsque les barres de contrôles standard sont activées ou désactivées ou lorsque la fenêtre frame est redimensionnée.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bNotify`  
 Détermine si l’élément actif sur place pour la fenêtre frame reçoit la notification de la modification de la disposition. Si **TRUE**, l’élément est notifié ; sinon **FALSE**.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction membre appelle le `CWnd` fonction membre `RepositionBars` pour repositionner toutes les barres de contrôle de l’image, ainsi que dans la fenêtre principale du client (généralement un `CView` ou **MDICLIENT**).  
  
 Remplacez cette fonction membre pour contrôler l’apparence et le comportement des barres de contrôle après modification de la disposition de la fenêtre frame. Par exemple, appeler lorsque vous activez ou désactiver les barres de contrôle ou ajoutez une autre barre de contrôle.  
  
##  <a name="a-namerectdefaulta--cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::rectDefault  
 Passer ce statique `CRect` en tant que paramètre lors de la création d’une fenêtre pour permettre à Windows de choisir la taille initiale et la position de la fenêtre.  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="a-namesavebarstatea--cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::SaveBarState  
 Appelez cette fonction pour stocker des informations sur chaque barre de contrôle appartient à la fenêtre frame.  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszProfileName`  
 Nom d’une section dans le fichier d’initialisation ou une clé dans le Registre Windows où sont stockées les informations d’état.  
  
### <a name="remarks"></a>Remarques  
 Ces informations peuvent être lues à partir du fichier d’initialisation en utilisant [LoadBarState](#loadbarstate). Informations stockées incluent la visibilité, l’orientation horizontal/vertical, station d’accueil d’état et la position de barre de contrôle.  
  
##  <a name="a-namesetactivepreviewviewa--cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 Désigne la vue spécifiée à la vue active pour l’aperçu riche.  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>Paramètres  
 `pViewNew`  
 Pointeur vers une vue à activer.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetactiveviewa--cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::SetActiveView  
 Appelez cette fonction membre pour définir la vue active.  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *pViewNew*  
 Spécifie un pointeur vers un [CView](../../mfc/reference/cview-class.md) objet, ou **NULL** pour aucune vue active.  
  
 `bNotify`  
 Spécifie si la vue doit être averti de l’activation. Si **TRUE**, `OnActivateView` est appelée pour le nouvel affichage ; si **FALSE**, il n’est pas.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction automatiquement lorsque l’utilisateur met le focus sur une vue dans la fenêtre frame. Vous pouvez appeler explicitement `SetActiveView` pour déplacer le focus vers la vue spécifiée.  
  
##  <a name="a-namesetdockstatea--cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState  
 Appelez cette fonction membre pour appliquer les informations d’état stockées dans un `CDockState` objet aux barres de contrôles de la fenêtre frame.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Paramètres  
 `state`  
 Appliquer l’état stocké aux barres de contrôles de la fenêtre frame.  
  
### <a name="remarks"></a>Remarques  
 Pour restaurer un état antérieur des barres de contrôles, vous pouvez charger l’état stocké avec `CDockState::LoadState` ou `Serialize`, puis utilisez `SetDockState` pour l’appliquer aux barres de contrôles de la fenêtre frame. L’état précédent est stocké dans le `CDockState` de l’objet avec`GetDockState`  
  
##  <a name="a-namesetmenubarstatea--cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 Définit l’état d’affichage du menu de l’application MFC actuelle masqués ou affichés.  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `nState`|Spécifie s’il faut afficher ou masquer le menu. Le `nState` paramètre peut avoir les valeurs suivantes :<br /><br /> -AFX_MBS_VISIBLE (0 x&01;) : affiche le menu s’il est masqué, mais n’a aucun effet s’il est visible.<br />-AFX_MBS_HIDDEN (0 x&02;) : masque le menu si elle est visible, mais n’a aucun effet s’il est masqué.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode modifie correctement l’état de menu ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si une erreur d’exécution se produit, cette méthode déclare en mode débogage et déclenche une exception dérivée de le [CException](../../mfc/reference/cexception-class.md) classe.  
  
##  <a name="a-namesetmenubarvisibilitya--cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 Définit le comportement par défaut du menu de l’application MFC actuelle pour être masquées ou visibles.  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `nStyle`|Spécifie si le menu est par défaut masqué, ou est visible et a le focus. Le `nStyle` paramètre peut avoir les valeurs suivantes :<br /><br /> -AFX_MBV_KEEPVISIBLE (0 X&01;) :<br />     Le menu est affiché en permanence et par défaut n’a pas le focus.<br />-AFX_MBV_DISPLAYONFOCUS (0 X&02;) :<br />     Le menu est masqué par défaut. Si le menu est masqué, appuyez sur la touche ALT pour afficher le menu et lui donner le focus. Si le menu s’affiche, appuyez sur ALT ou sur ÉCHAP pour masquer le menu.<br />-AFX_MBV_ DISPLAYONFOCUS (0 X&02;) | AFX_MBV_DISPLAYONF10 (0 X&04;)<br />     (combinaison de bits (OR)) - le menu est masqué par défaut. Si le menu est masqué, appuyez sur la touche F10 pour afficher le menu et lui donner le focus. Si le menu s’affiche, appuyez sur la touche F10 pour basculer le focus sur ou hors du menu. Le menu s’affiche jusqu'à ce que vous appuyez sur la touche ALT ou sur ÉCHAP pour la masquer.|  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de la `nStyle` paramètre n’est pas valide, cette méthode déclare en mode débogage et déclenche [CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md) en mode version finale. Dans le cas d’autres erreurs d’exécution, cette méthode déclare en mode débogage et déclenche une exception dérivée de le [CException](../../mfc/reference/cexception-class.md) classe.  
  
 Cette méthode affecte l’état des menus dans les applications écrites pour [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] et versions ultérieures.  
  
##  <a name="a-namesetmessagetexta--cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 Appelez cette fonction pour placer une chaîne dans le volet de barre d’état qui possède un ID égal à 0.  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszText`  
 Pointe vers la chaîne doit être placée sur la barre d’état.  
  
 `nID`  
 Chaîne d’ID de ressource de la chaîne à placer sur la barre d’état.  
  
### <a name="remarks"></a>Remarques  
 C’est généralement le plus à gauche et le plus long, le volet de la barre d’état.  
  
##  <a name="a-namesetprogressbarpositiona--cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 Définit la position actuelle de la barre de progression Windows 7 affichée la barre des tâches.  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>Paramètres  
 `nProgressPos`  
 Spécifie la position à définir. Il doit être dans la plage définie par `SetProgressBarRange`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetprogressbarrangea--cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 Définit la plage de la barre de progression Windows 7 affichée la barre des tâches.  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>Paramètres  
 `nRangeMin`  
 Valeur minimale.  
  
 `nRangeMax`  
 Valeur maximale.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetprogressbarstatea--cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 Définit le type et l’état de l’indicateur de progression affichée sur un bouton de barre des tâches.  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `tbpFlags`  
 Indicateurs qui contrôlent l’état actuel du bouton de progression. Spécifiez uniquement une de ces indicateurs, car tous les États sont mutuellement exclusives : TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettaskbaroverlayicona--cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 Surchargé. S’applique à un segment de recouvrement à un bouton de barre des tâches pour indiquer l’état de l’application ou pour informer l’utilisateur.  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDResource`  
 Spécifie l’ID de ressource d’une icône à utiliser en tant que la superposition. Consultez la description pour `hIcon` pour plus d’informations.  
  
 `lpcszDescr`  
 Pointeur vers une chaîne qui fournit une version texte de remplacement des informations fournies par la superposition, à des fins d’accessibilité.  
  
 `hIcon`  
 Handle de l’icône à utiliser en tant que la superposition. Il s’agit d’une petite icône, mesurer 16 x 16 pixels à 96 points par pouce (PPP). Si une icône de recouvrement est déjà appliquée sur le bouton de la barre des tâches, ce segment existant est remplacé. Cette valeur peut être `NULL`. Comment un `NULL` valeur est gérée varie selon que le bouton de la barre des tâches représente une fenêtre unique ou un groupe de windows. Il incombe à l’application appelante pour libérer `hIcon` lorsqu’il n’est plus nécessaire.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`en cas de réussite ; `FALSE` si la version du système d’exploitation est inférieure à Windows 7 ou si une erreur se produit la définition de l’icône.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettitlea--cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::SetTitle  
 Définit le titre de l’objet window.  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTitle`  
 Pointeur vers une chaîne de caractères contenant le titre de l’objet window.  
  
##  <a name="a-nameshowcontrolbara--cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 Appelez cette fonction membre pour afficher ou masquer la barre de contrôle.  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBar`  
 Pointeur vers la barre de contrôle doit être affiché ou masqué.  
  
 `bShow`  
 Si **TRUE**, spécifie que la barre de contrôle doit être affiché. Si **FALSE**, spécifie que la barre de contrôle est masqué.  
  
 *bDelay*  
 Si **TRUE**, retarder l’affichage de la barre de contrôle. Si **FALSE**, afficher le contrôle de barre immédiatement.  
  
##  <a name="a-nameshowownedwindowsa--cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 Appelez cette fonction membre pour afficher toutes les fenêtres qui sont des descendants de le `CFrameWnd` objet.  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>Paramètres  
 `bShow`  
 Spécifie si les fenêtres enfants doivent être affichées ou masquées.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd (classe)](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd (classe)](../../mfc/reference/cmdichildwnd-class.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)   
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)   
 [Structure de CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)

