---
title: Classe de CWinAppEx | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinAppEx
dev_langs:
- C++
helpviewer_keywords:
- CWinAppEx class
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
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
ms.openlocfilehash: 6931f1e794116882722e402c9cb95acec1ebdfd5
ms.lasthandoff: 02/24/2017

---
# <a name="cwinappex-class"></a>CWinAppEx (classe)
`CWinAppEx`gère l’état de l’application enregistre l’état dans le Registre, charge l’état à partir du Registre, initialise les gestionnaires d’application et fournit des liens vers ces mêmes gestionnaires d’applications.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](#cwinappex)|Construit un objet `CWinAppEx`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinAppEx::CleanState](#cleanstate)|Supprime les informations relatives à l’application à partir du Registre Windows.|  
|[CWinAppEx::EnableLoadWindowPlacement](#enableloadwindowplacement)|Spécifie si l’application chargera la taille initiale et l’emplacement de la fenêtre frame principale à partir du Registre.|  
|[CWinAppEx::EnableTearOffMenus](#enabletearoffmenus)|Permet les menus volants pour l’application.|  
|[CWinAppEx::EnableUserTools](#enableusertools)|Permet à l’utilisateur créer des commandes de menu personnalisé dans l’application.|  
|[CWinAppEx::ExitInstance](#exitinstance)|Appelé par l’infrastructure à partir du `Run` fonction membre pour quitter cette instance de l’application. (Substitue [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).)|  
|[CWinAppEx::GetBinary](#getbinary)|Lit des données binaires qui sont associées à la valeur de Registre spécifiée.|  
|[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)|Retourne un pointeur vers le global [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objet.|  
|[CWinAppEx::GetDataVersion](#getdataversion)||  
|[CWinAppEx::GetDataVersionMajor](#getdataversionmajor)|Retourne la version principale de l’application enregistrée dans le Registre Windows.|  
|[CWinAppEx::GetDataVersionMinor](#getdataversionminor)|Retourne la version secondaire de l’application enregistrée dans le Registre Windows.|  
|[CWinAppEx::GetInt](#getint)|Lit les données numériques qui sont associées à la valeur spécifiée à partir du Registre.|  
|[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)|Retourne un pointeur vers le global [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) objet.|  
|[CWinAppEx::GetMouseManager](#getmousemanager)|Retourne un pointeur vers le global [CMouseManager](../../mfc/reference/cmousemanager-class.md) objet.|  
|[CWinAppEx::GetObject](#getobject)|Lit `CObject`-dérivées des données qui sont associées à la valeur spécifiée à partir du Registre.|  
|[CWinAppEx::GetRegSectionPath](#getregsectionpath)|Retourne une chaîne qui est le chemin d’accès d’une clé de Registre. Ce chemin d’accès concatène le chemin d’accès relatif fourni avec le chemin d’accès de l’application.|  
|[CWinAppEx::GetRegistryBase](#getregistrybase)|Retourne le chemin d’accès du Registre pour l’application.|  
|[CWinAppEx::GetSectionBinary](#getsectionbinary)|Lit des données binaires qui sont associées à la clé spécifiée et la valeur à partir du Registre.|  
|[CWinAppEx::GetSectionInt](#getsectionint)|Lit les données numériques à partir du Registre associé à la clé spécifiée et la valeur.|  
|[CWinAppEx::GetSectionObject](#getsectionobject)|Lit `CObject` données associé à la clé spécifiée et la valeur à partir du Registre.|  
|[CWinAppEx::GetSectionString](#getsectionstring)|Lit les données de chaîne qui sont associées à la clé spécifiée et la valeur à partir du Registre.|  
|[CWinAppEx::GetShellManager](#getshellmanager)|Retourne un pointeur vers le global [CShellManager](../../mfc/reference/cshellmanager-class.md) objet.|  
|[CWinAppEx::GetString](#getstring)|Lit les données de chaîne qui sont associées à la valeur spécifiée à partir du Registre.|  
|[CWinAppEx::GetTooltipManager](#gettooltipmanager)|Retourne un pointeur vers le global [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) objet.|  
|[CWinAppEx::GetUserToolsManager](#getusertoolsmanager)|Retourne un pointeur vers le global [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) objet.|  
|[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)|Initialise le `CContextMenuManager` objet.|  
|[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)|Initialise le `CKeyboardManager` objet.|  
|[CWinAppEx::InitMouseManager](#initmousemanager)|Initialise le `CMouseManager` objet.|  
|[CWinAppEx::InitShellManager](#initshellmanager)|Initialise le `CShellManager` (classe)|  
|[CWinAppEx::InitTooltipManager](#inittooltipmanager)|Initialise la `CTooltipManager` classe.|  
|[CWinAppEx::IsResourceSmartUpdate](#isresourcesmartupdate)||  
|[CWinAppEx::IsStateExists](#isstateexists)|Indique si la clé spécifiée est dans le Registre.|  
|[CWinAppEx::LoadState](#loadstate)|Charge l’état de l’application à partir du Registre.|  
|[CWinAppEx::OnAppContextHelp](#onappcontexthelp)|Appelé par l’infrastructure lorsque l’utilisateur demande l’aide contextuelle pour les **personnalisation** boîte de dialogue.|  
|[CWinAppEx::OnViewDoubleClick](#onviewdoubleclick)|Appelle la commande défini par l’utilisateur lorsque l’utilisateur double-clique sur n’importe où dans l’application.|  
|[CWinAppEx::OnWorkspaceIdle](#onworkspaceidle)||  
|[CWinAppEx::SaveState](#savestate)|Écrit l’état de l’infrastructure d’application dans le Registre Windows.|  
|[CWinAppEx::SetRegistryBase](#setregistrybase)|Définit le chemin d’accès de la clé de Registre par défaut. Cette clé sera utilisée comme une racine pour tous les appels de Registre suivantes.|  
|[CWinAppEx::ShowPopupMenu](#showpopupmenu)|Affiche un menu contextuel.|  
|[CWinAppEx::WriteBinary](#writebinary)|Écrit les données binaires à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteInt](#writeint)|Écrit les données numériques à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteObject](#writeobject)|Écrit des données qui sont dérivées de la [classe CObject](../../mfc/reference/cobject-class.md) à la valeur de Registre spécifiée.|  
|[CWinAppEx::WriteSectionBinary](#writesectionbinary)|Écrit les données binaires dans une valeur de clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionInt](#writesectionint)|Écrit les données numériques dans une valeur de clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionObject](#writesectionobject)|Écrit des données dérivées de la `CObject` classe vers une valeur de clé de Registre spécifiée.|  
|[CWinAppEx::WriteSectionString](#writesectionstring)|Écrit les données de chaîne en valeur de la clé de Registre spécifiée.|  
|[CWinAppEx::WriteString](#writestring)|Écrit les données de chaîne à la valeur de Registre spécifiée.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](#loadcustomstate)|Appelé par l’infrastructure lorsque l’état de l’application a été chargé.|  
|[CWinAppEx::LoadWindowPlacement](#loadwindowplacement)|Appelé par l’infrastructure lors du chargement de la taille et l’emplacement de votre application à partir du Registre. Les données chargées incluent la taille et l’emplacement du frame principal au moment de la dernière fermeture de votre application.|  
|[CWinAppEx::OnClosingMainFrame](#onclosingmainframe)|Appelé par l’infrastructure lors du traite d’une fenêtre frame principale `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](#preloadstate)|Appelé par le framework immédiatement avant l’état de l’application est chargée.|  
|[CWinAppEx::PreSaveState](#presavestate)|Appelé par le framework immédiatement avant l’état de l’application est enregistré.|  
|[CWinAppEx::ReloadWindowPlacement](#reloadwindowplacement)|Recharge la taille et l’emplacement de la fenêtre fournie à partir du Registre|  
|[CWinAppEx::SaveCustomState](#savecustomstate)|Appelé par l’infrastructure une fois qu’il écrit l’état de l’application dans le Registre.|  
|[CWinAppEx::StoreWindowPlacement](#storewindowplacement)|Appelée par l’infrastructure pour écrire la taille et l’emplacement du frame principal dans le Registre.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinAppEx::m_bForceImageReset](#m_bforceimagereset)|Spécifie si le framework réinitialise toutes les images de barre d’outils lorsque la fenêtre frame qui contient la barre d’outils est chargée.|  
  
## <a name="remarks"></a>Remarques  
 Nombre des fonctionnalités fournies par l’infrastructure MFC dépend de la `CWinAppEx` classe. Vous pouvez incorporer la `CWinAppEx` classe dans votre application de deux manières :  
  
-   Construire un `CWinAppEx` classe dans le thread principal.  
  
-   Dérive de la classe principale de l’application `CWinAppEx`.  
  
 Une fois que vous intégrez `CWinAppEx` dans votre application, vous pouvez initialiser l’un des responsables de l’application. Avant d’utiliser un gestionnaire d’application, vous devez l’initialiser en appelant la méthode initialize approprié. Pour obtenir un pointeur vers un gestionnaire spécifique, appelez la méthode get associée. Le `CWinAppEx` classe gère les gestionnaires d’application suivants : [CMouseManager classe](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager classe](../../mfc/reference/cusertoolsmanager-class.md), et [CMenuTearOffManager classe](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinappex.h  
  
##  <a name="a-namecleanstatea--cwinappexcleanstate"></a><a name="cleanstate"></a>CWinAppEx::CleanState  
 Supprime toutes les informations sur l’application à partir du Registre Windows.  
  
```  
virtual BOOL CleanState(LPCTSTR lpszSectionName=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSectionName`  
 Chaîne qui contient un chemin d’accès d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode efface les données d’application à partir d’une section spécifique du Registre. Vous pouvez spécifier la section Effacer à l’aide du paramètre `lpszSectionName`. Si `lpszSectionName` est `NULL`, cette méthode utilise le chemin d’accès du Registre par défaut stocké dans le `CWinAppEx` objet. Pour obtenir le chemin d’accès du Registre par défaut, utilisez [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="a-namecwinappexa--cwinappexcwinappex"></a><a name="cwinappex"></a>CWinAppEx::CWinAppEx  
 Construit un objet `CWinAppEx`.  
  
```  
CWinAppEx(BOOL bResourceSmartUpdate = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bResourceSmartUpdate`  
 Un paramètre booléen qui indique si l’objet de l’espace de travail doit détecter et gérer les mises à jour de la ressource.  
  
### <a name="remarks"></a>Notes  
 La `CWinAppEx` classe a des méthodes d’initialisation, fournit des fonctionnalités pour enregistrer et charger des informations d’application dans le Registre et de contrôler les paramètres d’application globale. Il vous permet également d’utiliser des gestionnaires globales tel que le [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md) et [CUserToolsManager classe](../../mfc/reference/cusertoolsmanager-class.md). Chaque application peut avoir qu’une seule instance de la `CWinAppEx` classe.  
  
##  <a name="a-nameenableloadwindowplacementa--cwinappexenableloadwindowplacement"></a><a name="enableloadwindowplacement"></a>CWinAppEx::EnableLoadWindowPlacement  
 Spécifie si l’application chargera la taille initiale et l’emplacement de la fenêtre frame principale à partir du Registre.  
  
```  
void EnableLoadWindowPlacement(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bEnable`  
 Spécifie si l’application charge la taille initiale et l’emplacement de la fenêtre frame principale à partir du Registre.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, la taille et l’emplacement du frame principal est chargé à partir du Registre ainsi que les autres paramètres de l’application. Cela se produit au cours de [CWinAppEx::LoadState](#loadstate). Si vous ne souhaitez pas charger le positionnement de la fenêtre initiale à partir du Registre, appelez cette méthode avec `bEnable` la valeur `false`.  
  
##  <a name="a-nameenabletearoffmenusa--cwinappexenabletearoffmenus"></a><a name="enabletearoffmenus"></a>CWinAppEx::EnableTearOffMenus  
 Crée et initialise un [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) objet.  
  
```  
BOOL EnableTearOffMenus(
    LPCTSTR lpszRegEntry,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszRegEntry`  
 Chaîne qui contient le chemin d’accès d’une clé de Registre. L’application utilise cette clé de Registre pour stocker des informations sur les menus détachables.  
  
 [in] `uiCmdFirst`  
 ID de menu est détachables.  
  
 [in] `uiCmdLast`  
 ID de la dernière détachables menu.  
  
### <a name="return-value"></a>Valeur de retour  
 `True`Si la `CMenuTearOffManager` est créé et initialisé avec succès ; `false` si une erreur se produit ou si le `CMenuTearOffManager` existe déjà.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour activer les menus volants dans votre application. Vous devez appeler cette fonction à partir de `InitInstance`.  
  
##  <a name="a-nameenableusertoolsa--cwinappexenableusertools"></a><a name="enableusertools"></a>CWinAppEx::EnableUserTools  
 Permet à l’utilisateur à créer des commandes de menu personnalisé qui réduisent les séquences de touches dans votre application. Cette méthode crée un [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) objet.  
  
```  
BOOL EnableUserTools(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC = RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID = 0,  
    UINT uInitDirMenuID = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdToolsDummy`  
 Entier non signé par le framework comme espace réservé pour l’ID de commande du menu outils utilisateur.  
  
 [in] `uiCmdFirst`  
 L’ID de commande pour la première commande de l’outil utilisateur.  
  
 [in] `uiCmdLast`  
 L’ID de commande pour la dernière commande d’outil utilisateur.  
  
 [in] `pToolRTC`  
 Une classe qui le `CUserToolsManager` objet utilise pour créer de nouveaux outils utilisateur.  
  
 [in] `uArgMenuID`  
 L’ID de menu argument.  
  
 [in] `uInitDirMenuID`  
 L’ID de menu pour le répertoire de l’outil initial.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la méthode crée et initialise un `CUserToolsManager` de l’objet ; `FALSE` si la méthode échoue ou si un `CUserToolsManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous activez les outils définis par l’utilisateur, le framework prend en charge automatiquement un menu dynamique qui peut être étendu pendant la personnalisation. Le framework associe chaque nouvel élément à une commande externe. Le framework appelle ces commandes lorsque l’utilisateur sélectionne l’élément approprié à partir de la **outils** menu.  
  
 Chaque fois que l’utilisateur ajoute un nouvel élément, l’infrastructure crée un nouvel objet. Le type de classe pour le nouvel objet est défini par `pToolRTC`. Le `pToolRTC` type de classe doit être dérivé de la [CUserTool classe](../../mfc/reference/cusertool-class.md).  
  
 Pour plus d’informations sur les outils de l’utilisateur et à les intégrer à votre application, consultez la page [outils définis par l’utilisateur](../../mfc/user-defined-tools.md).  
  
##  <a name="a-nameexitinstancea--cwinappexexitinstance"></a><a name="exitinstance"></a>CWinAppEx::ExitInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetbinarya--cwinappexgetbinary"></a><a name="getbinary"></a>CWinAppEx::GetBinary  
 Lit des données binaires à partir d’une clé de Registre spécifiée.  
  
```  
BOOL GetBinary(
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [out] `ppData`  
 Pointeur vers la mémoire tampon que la méthode remplit avec les données binaires.  
  
 [out] `pBytes`  
 Pointeur vers un entier non signé par la méthode pour écrire le nombre d’octets lus.  
  
### <a name="return-value"></a>Valeur de retour  
 `True`en cas de réussite ; `false` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode lit des données binaires écrites dans le Registre. Pour écrire des données dans le Registre, utilisez les méthodes [CWinAppEx::WriteBinary](#writebinary) et [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre située sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetcontextmenumanagera--cwinappexgetcontextmenumanager"></a><a name="getcontextmenumanager"></a>CWinAppEx::GetContextMenuManager  
 Retourne un pointeur vers le global [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objet.  
  
```  
CContextMenuManager* GetContextMenuManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CContextMenuManager` objet.  
  
### <a name="remarks"></a>Remarques  
 Si l’objet CContextMenuManager n’est pas initialisé, cette fonction appelle [CWinAppEx::InitContextMenuManager](#initcontextmenumanager) avant de retourner un pointeur.  
  
##  <a name="a-namegetdataversiona--cwinappexgetdataversion"></a><a name="getdataversion"></a>CWinAppEx::GetDataVersion  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetDataVersion() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetdataversionmajora--cwinappexgetdataversionmajor"></a><a name="getdataversionmajor"></a>CWinAppEx::GetDataVersionMajor  
 Retourne la version principale de l’application qui est enregistrée dans le Registre Windows lorsque vous appelez [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMajor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur entière qui contient le numéro de version principale.  
  
##  <a name="a-namegetdataversionminora--cwinappexgetdataversionminor"></a><a name="getdataversionminor"></a>CWinAppEx::GetDataVersionMinor  
 Retourne la version secondaire de l’application qui est enregistrée dans le Registre Windows lorsque vous appelez [CWinAppEx::SaveState](#savestate).  
  
```  
int GetDataVersionMinor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur entière qui contient le numéro de version secondaire.  
  
##  <a name="a-namegetinta--cwinappexgetint"></a><a name="getint"></a>CWinAppEx::GetInt  
 Lit les données d’entier d’une clé de Registre spécifiée.  
  
```  
int GetInt(
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une entrée de Registre.  
  
 [in] `nDefault`  
 La valeur par défaut retourné par la méthode si l’entrée de Registre spécifiée n’existe pas.  
  
### <a name="return-value"></a>Valeur de retour  
 Les données du Registre, si la méthode a réussi ; dans le cas contraire `nDefault`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode lit des données de type entier à partir du Registre. Si aucune donnée entier associé à la clé de Registre indiquée par `lpszEntry`, cette méthode retourne `nDefault`. Pour écrire des données dans le Registre, utilisez les méthodes [CWinAppEx::WriteSectionInt](#writesectionint) et [CWinAppEx::WriteInt](#writeint).  
  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre située sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetkeyboardmanagera--cwinappexgetkeyboardmanager"></a><a name="getkeyboardmanager"></a>CWinAppEx::GetKeyboardManager  
 Retourne un pointeur vers le global [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) objet.  
  
```  
CKeyboardManager* GetKeyboardManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CKeyboardManager` objet.  
  
### <a name="remarks"></a>Remarques  
 Si le Gestionnaire de clavier n’est pas initialisé, cette fonction appelle [CWinAppEx::InitKeyboardManager](#initkeyboardmanager) avant de retourner un pointeur.  
  
##  <a name="a-namegetmousemanagera--cwinappexgetmousemanager"></a><a name="getmousemanager"></a>CWinAppEx::GetMouseManager  
 Retourne un pointeur vers le global [CMouseManager](../../mfc/reference/cmousemanager-class.md) objet.  
  
```  
CMouseManager* GetMouseManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CMouseManager` objet.  
  
### <a name="remarks"></a>Remarques  
 Si le Gestionnaire de souris n’est pas initialisé, cette fonction appelle [CWinAppEx::InitMouseManager](#initmousemanager) avant de retourner un pointeur.  
  
##  <a name="a-namegetobjecta--cwinappexgetobject"></a><a name="getobject"></a>CWinAppEx::GetObject  
 Lit [CObject](../../mfc/reference/cobject-class.md)- dervied des données à partir du Registre.  
  
```  
BOOL GetObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le chemin d’accès relatif d’une entrée de Registre.  
  
 [out] `obj`  
 Une référence à un `CObject`. La méthode utilise cette référence pour stocker les données du Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode lit les données à partir du Registre qui est dérivé de `CObject`. Pour écrire `CObject` les données dans le Registre, utilisez [CWinAppEx::WriteObject](#writeobject) ou [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre qui se trouve sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetregistrybasea--cwinappexgetregistrybase"></a><a name="getregistrybase"></a>CWinAppEx::GetRegistryBase  
 Récupère le chemin d’accès du Registre par défaut pour l’application.  
  
```  
LPCTSTR GetRegistryBase();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui contient le chemin d’accès de l’emplacement de Registre par défaut.  
  
### <a name="remarks"></a>Remarques  
 Toutes les méthodes de la [CWinAppEx classe](../../mfc/reference/cwinappex-class.md) qui accèdent le début du Registre dans un emplacement par défaut. Utilisez cette méthode pour récupérer un chemin d’accès de l’emplacement de Registre par défaut. Utilisez [CWinAppEx::SetRegistryBase](#setregistrybase) pour modifier l’emplacement de Registre par défaut.  
  
##  <a name="a-namegetregsectionpatha--cwinappexgetregsectionpath"></a><a name="getregsectionpath"></a>CWinAppEx::GetRegSectionPath  
 Crée et retourne le chemin d’accès absolu d’une clé de Registre.  
  
```  
CString GetRegSectionPath(LPCTSTR szSectionAdd = _T(""));
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `szSectionAdd`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` qui contient le chemin d’accès absolu d’une clé de Registre.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode définit le chemin d’accès absolu de la clé de Registre en ajoutant le chemin d’accès relatif dans `szSectionAdd` à l’emplacement de Registre par défaut pour votre application. Pour obtenir la clé de Registre par défaut, utilisez la méthode [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
##  <a name="a-namegetsectionbinarya--cwinappexgetsectionbinary"></a><a name="getsectionbinary"></a>CWinAppEx::GetSectionBinary  
 Lit des données binaires à partir du Registre.  
  
```  
BOOL GetSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à lire.  
  
 [out] `ppData`  
 Pointeur vers la mémoire tampon dans laquelle la méthode stocke les données.  
  
 [out] `pBytes`  
 Pointeur vers un entier non signé. La méthode écrit la taille de `ppData` à ce paramètre.  
  
### <a name="return-value"></a>Valeur de retour  
 `True` en cas de réussite ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode lit des données binaires qui sont écrites dans le Registre à l’aide des méthodes [CWinAppEx::WriteBinary](#writebinary) et [CWinAppEx::WriteSectionBinary](#writesectionbinary).  
  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetsectioninta--cwinappexgetsectionint"></a><a name="getsectionint"></a>CWinAppEx::GetSectionInt  
 Lit les données de type entier dans le Registre.  
  
```  
int GetSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à lire.  
  
 [in] `nDefault`  
 La valeur par défaut à retourner si la valeur spécifiée n’existe pas.  
  
### <a name="return-value"></a>Valeur de retour  
 Les données d’entier qui sont stockées dans la valeur de Registre spécifiée. `nDefault` si les données n’existent pas.  
  
### <a name="remarks"></a>Notes  
 Utilisez les méthodes [CWinAppEx::WriteInt](#writeint) et [CWinAppEx::WriteSectionInt](#writesectionint) pour écrire les données de type entier dans le Registre.  
  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu d’une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetsectionobjecta--cwinappexgetsectionobject"></a><a name="getsectionobject"></a>CWinAppEx::GetSectionObject  
 Lit [CObject](../../mfc/reference/cobject-class.md) les données du Registre à partir du Registre.  
  
```  
BOOL GetSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à lire.  
  
 [out] `obj`  
 Une référence à un `CObject`. Utilise la méthode `CObject` pour stocker les données du Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode lit les données à partir du Registre. Les données lues est `CObject` données, ou pour une classe dérivée de `CObject`. Pour écrire `CObject` les données dans le Registre, utilisez [CWinAppEx::WriteObject](#writeobject) ou [CWinAppEx::WriteSectionObject](#writesectionobject).  
  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetsectionstringa--cwinappexgetsectionstring"></a><a name="getsectionstring"></a>CWinAppEx::GetSectionString  
 Lit les données à partir du Registre de chaîne.  
  
```  
CString GetSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = _T(""));
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à lire.  
  
 [in] `lpszDefault`  
 La valeur par défaut à retourner si la valeur spécifiée n’existe pas.  
  
### <a name="return-value"></a>Valeur de retour  
 Les données de chaîne stockées dans la valeur de Registre spécifiée si les données existent ; dans le cas contraire `lpszDefault`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode lit les données de chaîne écrites dans le Registre. Utilisez [CWinAppEx::WriteString](#writestring) et [CWinAppEx::WriteSectionString](#writesectionstring) pour écrire les données de chaîne dans le Registre.  
  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegetshellmanagera--cwinappexgetshellmanager"></a><a name="getshellmanager"></a>CWinAppEx::GetShellManager  
 Retourne un pointeur vers le global [CShellManager](../../mfc/reference/cshellmanager-class.md) objet.  
  
```  
CShellManager* GetShellManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CShellManager` objet.  
  
### <a name="remarks"></a>Notes  
 Si le `CShellManager` objet n’est pas initialisé, cette fonction appelle [CWinAppEx::InitShellManager](#initshellmanager) avant de retourner un pointeur.  
  
##  <a name="a-namegetstringa--cwinappexgetstring"></a><a name="getstring"></a>CWinAppEx::GetString  
 Lectures chaîne les données à partir d’une clé de Registre spécifiée.  
  
```  
CString GetString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpzDefault= _T(""));
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une clé de Registre  
  
 [in] `lpzDefault`  
 La valeur par défaut retourné par la méthode si l’entrée de Registre spécifiée n’existe pas.  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne de données stockées dans le Registre en cas de réussite ; `lpszDefault` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode lit les données de chaîne écrites dans le Registre. Pour écrire des données dans le Registre, utilisez les méthodes [CWinAppEx::WriteString](#writestring) ou [CWinAppEx::WriteSectionString](#writesectionstring).  
  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre située sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namegettooltipmanagera--cwinappexgettooltipmanager"></a><a name="gettooltipmanager"></a>CWinAppEx::GetTooltipManager  
 Retourne un pointeur vers le global [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) objet.  
  
```  
CTooltipManager* GetTooltipManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CTooltipManager` objet.  
  
### <a name="remarks"></a>Remarques  
 Si le `CTooltipManager` objet n’est pas initialisé, cette fonction appelle [CWinAppEx::InitTooltipManager](#inittooltipmanager) avant de retourner un pointeur.  
  
##  <a name="a-namegetusertoolsmanagera--cwinappexgetusertoolsmanager"></a><a name="getusertoolsmanager"></a>CWinAppEx::GetUserToolsManager  
 Retourne un pointeur vers le global [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) objet.  
  
```  
CUserToolsManager* GetUserToolsManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le global `CUserToolsManager` de l’objet ; `NULL` si la gestion des outils utilisateur n’est pas activée pour l’application.  
  
### <a name="remarks"></a>Remarques  
 Avant de récupérer un pointeur vers le `CUserToolsManager` de l’objet, vous devez initialiser le gestionnaire en appelant [CWinAppEx::EnableUserTools](#enableusertools).  
  
##  <a name="a-nameinitcontextmenumanagera--cwinappexinitcontextmenumanager"></a><a name="initcontextmenumanager"></a>CWinAppEx::InitContextMenuManager  
 Initialise le [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objet.  
  
```  
BOOL InitContextMenuManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode crée l’objet CContextMenuManager ; 0 si le `CContextMenuManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Notes  
 Si vous appelez [CWinAppEx::GetContextMenuManager](#getcontextmenumanager), l’implémentation par défaut de cette méthode appelle `InitContextMenuManager`.  
  
 Si votre application possède déjà un gestionnaire de menu contextuel et que vous appelez `InitContextMenuManager`, votre application aura une [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) échec. Par conséquent, vous ne devez pas appeler `InitContextMenuManager` si vous créez un `CContextMenuManager` directement l’objet. Si vous n’utilisez pas personnalisé `CContextMenuManager`, vous devez utiliser `GetContextMenuManager` pour créer un `CContextMenuManager` objet.  
  
##  <a name="a-nameinitkeyboardmanagera--cwinappexinitkeyboardmanager"></a><a name="initkeyboardmanager"></a>CWinAppEx::InitKeyboardManager  
 Initialise le [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) objet.  
  
```  
BOOL InitKeyboardManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode crée le `CKeyboardManager` objet ; 0 si le `CKeyboardManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Notes  
 Si vous appelez [CWinAppEx::GetKeyboardManager](#getkeyboardmanager), l’implémentation par défaut de cette méthode appelle `InitKeyboardManager`.  
  
 Si votre application possède déjà un gestionnaire de clavier et que vous appelez `InitKeyboardManager`, votre application aura une [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) échec. Par conséquent, vous ne devez pas appeler `InitKeyboardManager` si vous créez un `CKeyboardManager` directement l’objet. Si vous n’utilisez pas personnalisé `CKeyboardManager`, vous devez utiliser `GetKeyboardManager` pour créer un `CKeyboardManager` objet.  
  
##  <a name="a-nameinitmousemanagera--cwinappexinitmousemanager"></a><a name="initmousemanager"></a>CWinAppEx::InitMouseManager  
 Initialise le [CMouseManager](../../mfc/reference/cmousemanager-class.md) objet.  
  
```  
BOOL InitMouseManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode crée le `CMouseManager` objet ; 0 si le `CMouseManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Remarques  
 Si vous appelez [CWinAppEx::GetMouseManager](#getmousemanager), l’implémentation par défaut de cette méthode appelle `InitMouseManager`.  
  
 Si votre application possède déjà un gestionnaire de souris et que vous appelez `InitMouseManager`, votre application aura une [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) échec. Par conséquent, vous ne devez pas appeler `InitMouseManager` si vous créez un `CMouseManager` directement l’objet. Si vous n’utilisez pas personnalisé `CMouseManager`, vous devez utiliser `GetMouseManager` pour créer un `CMouseManager` objet.  
  
##  <a name="a-nameinitshellmanagera--cwinappexinitshellmanager"></a><a name="initshellmanager"></a>CWinAppEx::InitShellManager  
 Initialise le [CShellManager](../../mfc/reference/cshellmanager-class.md) objet.  
  
```  
BOOL InitShellManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode crée le `CShellManager` objet ; 0 si le `CShellManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Remarques  
 Si vous appelez [CWinAppEx::GetShellManager](#getshellmanager), l’implémentation par défaut de cette méthode appelle `InitShellManager`.  
  
 Si votre application possède déjà un gestionnaire de l’interpréteur de commandes et que vous appelez `InitShellManager`, votre application déclenche une [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) échec. Par conséquent, n’appelez pas `InitShellManager` si vous créez un `CShellManager` directement l’objet. Si vous n’utilisez pas personnalisé `CShellManager`, utilisez `GetShellManager` pour créer un `CShellManager` objet.  
  
##  <a name="a-nameinittooltipmanagera--cwinappexinittooltipmanager"></a><a name="inittooltipmanager"></a>CWinAppEx::InitTooltipManager  
 Initialise le [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) objet.  
  
```  
BOOL InitTooltipManager();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode crée le `CTooltipManager` objet ; 0 si le `CTooltipManager` l’objet existe déjà.  
  
### <a name="remarks"></a>Notes  
 Si vous appelez [CWinAppEx::GetTooltipManager](#gettooltipmanager), l’implémentation par défaut de cette méthode appelle `InitTooltipManager`.  
  
 Si votre application possède déjà un gestionnaire d’info-bulle et que vous appelez `InitTooltipManager`, votre application aura une [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) échec. Par conséquent, vous ne devez pas appeler `InitTooltipManager` si vous créez un `CTooltipManager` directement l’objet. Si vous n’utilisez pas personnalisé `CTooltipManager`, vous devez utiliser `GetTooltipManager` pour créer un `CTooltipManager` objet.  
  
##  <a name="a-nameisresourcesmartupdatea--cwinappexisresourcesmartupdate"></a><a name="isresourcesmartupdate"></a>CWinAppEx::IsResourceSmartUpdate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResourceSmartUpdate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisstateexistsa--cwinappexisstateexists"></a><a name="isstateexists"></a>CWinAppEx::IsStateExists  
 Indique si la clé spécifiée est dans le Registre.  
  
```  
BOOL IsStateExists(LPCTSTR lpszSectionName);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSectionName`  
 Chaîne qui contient un chemin d’accès d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la clé dans le Registre. sinon 0.  
  
##  <a name="a-nameloadcustomstatea--cwinappexloadcustomstate"></a><a name="loadcustomstate"></a>CWinAppEx::LoadCustomState  
 Le framework appelle cette méthode après avoir chargé l’état de l’application à partir du Registre.  
  
```  
virtual void LoadCustomState();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode si vous souhaitez effectuer tout traitement une fois l’application chargée de l’état à partir du Registre. Par défaut, cette méthode ne fait rien.  
  
 Pour charger les informations d’état personnalisées à partir du Registre, les informations doivent tout d’abord être enregistrées à l’aide de [CWinAppEx::SaveCustomState](#savecustomstate).  
  
##  <a name="a-nameloadstatea--cwinappexloadstate"></a><a name="loadstate"></a>CWinAppEx::LoadState  
 Lit l’état de l’application à partir du Registre Windows.  
  
```  
BOOL LoadState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
virtual BOOL LoadState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFrame`  
 Pointeur vers un objet fenêtre frame. La méthode applique les informations d’état dans le Registre pour cette fenêtre frame.  
  
 [in] `lpszSectionName`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `pFrameImpl`  
 Un pointeur vers un `CFrameImpl` objet. La méthode applique les informations d’état dans le Registre pour cette fenêtre frame.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Cette méthode charge l’état de l’application et les informations d’état pour une fenêtre frame. Les informations chargées de la fenêtre frame sont appliquées à la fenêtre frame fourni. Si vous ne fournissez pas une fenêtre frame, uniquement les informations d’état application sont chargées. Les informations d’application incluent l’état de la [CMouseManager classe](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md)et [CUserToolsManager classe](../../mfc/reference/cusertoolsmanager-class.md).  
  
 L’implémentation par défaut de `CFrameImpl::OnLoadFrame` appelle `LoadState`.  
  
 Le `lpszSectionName` paramètre n’est pas le chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-nameloadwindowplacementa--cwinappexloadwindowplacement"></a><a name="loadwindowplacement"></a>CWinAppEx::LoadWindowPlacement  
 Appelé par l’infrastructure lors du chargement de la taille et l’emplacement de la fenêtre frame principale à partir du Registre.  
  
```  
virtual BOOL LoadWindowPlacement(
    CRect& rectNormalPosition,  
    int& nFlags,  
    int& nShowCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `rectNormalPosition`  
 Un rectangle qui contient les coordonnées de la fenêtre frame principale lorsqu’il est à la position restaurée.  
  
 [out] `nFlags`  
 Indicateurs qui contrôlent la position de la fenêtre réduite et la façon dont le système d’exploitation bascule entre une fenêtre réduite et une fenêtre restaurée.  
  
 [out] `nShowCmd`  
 Entier qui spécifie l’état d’affichage de la fenêtre. Pour plus d’informations sur les valeurs possibles, consultez la page [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Par défaut, MFC charge automatiquement la position précédente et l’état de la fenêtre frame principale lorsque l’application démarre. Pour plus d’informations sur la façon dont ces informations sont stockées dans le Registre, consultez la page [CWinAppEx::StoreWindowPlacement](#storewindowplacement).  
  
 Substituez cette méthode si vous souhaitez charger plus d’informations sur la fenêtre frame principale.  
  
##  <a name="a-namembforceimagereseta--cwinappexmbforceimagereset"></a><a name="m_bforceimagereset"></a>CWinAppEx::m_bForceImageReset  
 Spécifie si le framework réinitialise toutes les images de barre d’outils lorsqu’il recharge la fenêtre frame qui contient la barre d’outils.  
  
```  
BOOL m_bForceImageReset;  
```  
  
### <a name="remarks"></a>Remarques  
 Le `m_bForceImageReset` membre de données est une variable protégée.  
  
##  <a name="a-nameonappcontexthelpa--cwinappexonappcontexthelp"></a><a name="onappcontexthelp"></a>CWinAppEx::OnAppContextHelp  
 Le framework appelle cette méthode lorsque l’utilisateur demande l’aide contextuelle pour les **personnalisation** boîte de dialogue.  
  
```  
virtual void OnAppContextHelp(
    CWnd* pWndControl,  
    const DWORD dwHelpIDArray[]);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWndControl`  
 Pointeur vers un objet de fenêtre pour laquelle l’utilisateur appelée aide contextuelle.  
  
 [in] `dwHelpIDArray[]`  
 Une valeur réservée.  
  
### <a name="remarks"></a>Remarques  
 Actuellement, cette méthode est réservée pour une utilisation ultérieure. L’implémentation par défaut ne fait rien et il n’est actuellement pas appelée par l’infrastructure.  
  
##  <a name="a-nameonclosingmainframea--cwinappexonclosingmainframe"></a><a name="onclosingmainframe"></a>CWinAppEx::OnClosingMainFrame  
 Le framework appelle cette méthode lors du traite d’une fenêtre frame `WM_CLOSE`.  
  
```  
virtual void OnClosingMainFrame(CFrameImpl* pFrameImpl);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFrameImpl`  
 Un pointeur vers un `CFrameImpl` objet.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette méthode enregistre l’état de `pFrameImpl`.  
  
##  <a name="a-nameonviewdoubleclicka--cwinappexonviewdoubleclick"></a><a name="onviewdoubleclick"></a>CWinAppEx::OnViewDoubleClick  
 Appelle la commande défini par l’utilisateur qui est associée à une vue lorsque l’utilisateur double-clique dans cette vue.  
  
```  
virtual BOOL OnViewDoubleClick(
    CWnd* pWnd,  
    int iViewId);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pWnd`  
 Un pointeur vers un objet dérivé de la [CView (classe)](../../mfc/reference/cview-class.md).  
  
 [in] `iViewId`  
 L’ID de la vue.  
  
### <a name="return-value"></a>Valeur de retour  
 `True`Si l’infrastructure trouve une commande ; Sinon, false.  
  
### <a name="remarks"></a>Remarques  
 Pour prendre en charge du comportement de la souris personnalisé, vous devez appeler cette fonction lorsque vous traitez le `WM_LBUTTONDBLCLK` message. Cette méthode exécute la commande associée à l’ID de vue fournie par `iViewId`. Pour plus d’informations sur le comportement de la souris personnalisé, consultez la page [personnalisation du clavier et souris](../../mfc/keyboard-and-mouse-customization.md).  
  
##  <a name="a-nameonworkspaceidlea--cwinappexonworkspaceidle"></a><a name="onworkspaceidle"></a>CWinAppEx::OnWorkspaceIdle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnWorkspaceIdle(CWnd*);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `CWnd*`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namepreloadstatea--cwinappexpreloadstate"></a><a name="preloadstate"></a>CWinAppEx::PreLoadState  
 Le framework appelle cette méthode immédiatement avant de charger l’état de l’application à partir du Registre.  
  
```  
virtual void PreLoadState();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode si vous souhaitez effectuer tout traitement immédiatement avant le charge de l’infrastructure de l’état de l’application.  
  
##  <a name="a-namepresavestatea--cwinappexpresavestate"></a><a name="presavestate"></a>CWinAppEx::PreSaveState  
 Le framework appelle cette méthode immédiatement avant d’enregistrer l’état de l’application.  
  
```  
virtual void PreSaveState();
```  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode si vous souhaitez effectuer tout traitement immédiatement avant le framework enregistre l’état de l’application.  
  
##  <a name="a-namereloadwindowplacementa--cwinappexreloadwindowplacement"></a><a name="reloadwindowplacement"></a>CWinAppEx::ReloadWindowPlacement  
 Recharge la taille et l’emplacement d’une fenêtre à partir du Registre.  
  
```  
virtual BOOL ReloadWindowPlacement(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pFrame`  
 Pointeur vers une fenêtre frame.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; 0 si le chargement a échoué ou il n’y a aucune donnée à charger.  
  
### <a name="remarks"></a>Remarques  
 Utilisez la fonction [CWinAppEx::StoreWindowPlacement](#storewindowplacement) pour écrire la taille et l’emplacement d’une fenêtre dans le Registre.  
  
##  <a name="a-namesavecustomstatea--cwinappexsavecustomstate"></a><a name="savecustomstate"></a>CWinAppEx::SaveCustomState  
 Le framework appelle cette méthode après que elle enregistre l’état de l’application dans le Registre.  
  
```  
virtual void SaveCustomState();
```  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode si vous souhaitez effectuer tout traitement une fois que l’application enregistre l’état dans le Registre. Par défaut, cette méthode ne fait rien.  
  
##  <a name="a-namesavestatea--cwinappexsavestate"></a><a name="savestate"></a>CWinAppEx::SaveState  
 Écrit l’état de l’application dans le Registre Windows.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);

 
BOOL SaveState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSectionName`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `pFrameImpl`  
 Un pointeur vers un `CFrameImpl` objet. Cette image est enregistrée dans le Registre Windows.  
  
 [in] `pFrame`  
 Pointeur vers un objet fenêtre frame. Cette image est enregistrée dans le Registre Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 `True`en cas de réussite ; `false` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode enregistre l’état de l’application et les informations d’état de la fenêtre frame fourni. Si vous ne fournissez pas une fenêtre frame, la méthode enregistre uniquement l’état de l’application. Les informations d’application incluent l’état de la [CMouseManager classe](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager classe](../../mfc/reference/ckeyboardmanager-class.md)et [CUserToolsManager classe](../../mfc/reference/cusertoolsmanager-class.md).  
  
 Le `lpszSectionName` paramètre n’est pas le chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
##  <a name="a-namesetregistrybasea--cwinappexsetregistrybase"></a><a name="setregistrybase"></a>CWinAppEx::SetRegistryBase  
 Définit le chemin d’accès du Registre par défaut pour l’application.  
  
```  
LPCTSTR SetRegistryBase(LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSectionName`  
 Chaîne qui contient le chemin d’accès d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui contient le chemin d’accès de l’emplacement de Registre par défaut.  
  
### <a name="remarks"></a>Remarques  
 Toutes les méthodes de la [CWinAppEx classe](../../mfc/reference/cwinappex-class.md) qui accèdent le début du Registre dans un emplacement par défaut. Utilisez cette méthode pour modifier cet emplacement de Registre par défaut. Utilisez [CWinAppEx::GetRegistryBase](#getregistrybase) pour extraire l’emplacement de Registre par défaut.  
  
##  <a name="a-nameshowpopupmenua--cwinappexshowpopupmenu"></a><a name="showpopupmenu"></a>CWinAppEx::ShowPopupMenu  
 Affiche un menu contextuel.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    const CPoint& point,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiMenuResId`  
 Un ID de ressource de menu.  
  
 [in] `point`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) qui spécifie la position du menu en coordonnées d’écran.  
  
 [in] `pWnd`  
 Pointeur vers la fenêtre propriétaire le menu contextuel.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le menu contextuel s’affiche avec succès ; 0 dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Cette méthode affiche le menu associé `uiMenuResId`.  
  
 Pour prendre en charge les menus contextuels, vous devez avoir un [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objet. Si vous n’avez pas initialisé la `CContextMenuManager` objet `ShowPopupMenu` échoue.  
  
##  <a name="a-namestorewindowplacementa--cwinappexstorewindowplacement"></a><a name="storewindowplacement"></a>CWinAppEx::StoreWindowPlacement  
 Appelée par l’infrastructure pour écrire la taille et l’emplacement de la fenêtre frame principale dans le Registre.  
  
```  
virtual BOOL StoreWindowPlacement(
    const CRect& rectNormalPosition,  
    int nFlags,  
    int nShowCmd);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nFlags`  
 Indicateurs qui contrôlent la position de la fenêtre réduite et la façon dont le système d’exploitation bascule entre une fenêtre réduite et une fenêtre restaurée.  
  
 [in] `nShowCmd`  
 Entier qui spécifie l’état d’affichage de la fenêtre. Pour plus d’informations sur les valeurs possibles, consultez la page [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow).  
  
 [in] `rectNormalPosition`  
 Un rectangle qui contient les coordonnées de la fenêtre frame principale lorsqu’il est dans son état restauré.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Par défaut, MFC enregistre automatiquement la position et l’état de la fenêtre frame principale avant la fermeture de l’application. Ces informations sont stockées dans le Registre Windows sous la clé WindowPlacement dans l’emplacement de Registre par défaut pour votre application. Pour plus d’informations sur l’emplacement de Registre par défaut de votre application, consultez la page [CWinAppEx::GetRegistryBase](#getregistrybase).  
  
 Substituez cette méthode si vous souhaitez stocker des informations supplémentaires sur la fenêtre frame principale.  
  
##  <a name="a-namewritebinarya--cwinappexwritebinary"></a><a name="writebinary"></a>CWinAppEx::WriteBinary  
 Écrit des données binaires dans le Registre.  
  
```  
BOOL WriteBinary(
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [in] `pData`  
 Les données à stocker.  
  
 [in] `nBytes`  
 La taille du `pData` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre qui se trouve sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
 Si la clé spécifiée par `lpszEntry` n’existe pas, cette méthode crée.  
  
##  <a name="a-namewriteinta--cwinappexwriteint"></a><a name="writeint"></a>CWinAppEx::WriteInt  
 Écrit des données numériques dans le Registre.  
  
```  
BOOL WriteInt(
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [in] `nValue`  
 Les données à stocker.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre située sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
 Si la clé spécifiée par `lpszEntry` n’existe pas, cette méthode crée.  
  
##  <a name="a-namewriteobjecta--cwinappexwriteobject"></a><a name="writeobject"></a>CWinAppEx::WriteObject  
 Écrit des données dérivées de la [classe CObject](../../mfc/reference/cobject-class.md) dans le Registre.  
  
```  
BOOL WriteObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à définir.  
  
 [in] `obj`  
 Une référence à `CObject` données qui stocke la méthode.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode écrit le `obj` les données à la valeur spécifiée dans la clé de Registre par défaut. Utilisez [CWinAppEx::GetRegistryBase](#getregistrybase) pour déterminer la clé de Registre actuelle.  
  
##  <a name="a-namewritesectionbinarya--cwinappexwritesectionbinary"></a><a name="writesectionbinary"></a>CWinAppEx::WriteSectionBinary  
 Écrit des données binaires à une valeur dans le Registre.  
  
```  
BOOL WriteSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le nom d’une clé de Registre  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à définir.  
  
 [in] `pData`  
 Les données à écrire dans le Registre.  
  
 [in] `nBytes`  
 La taille du `pData` en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Le `lpszSubSection` paramètre n’est pas le chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
 Si la clé spécifiée par `lpszEntry` n’existe pas, cette méthode crée.  
  
##  <a name="a-namewritesectioninta--cwinappexwritesectionint"></a><a name="writesectionint"></a>CWinAppEx::WriteSectionInt  
 Écrit des données numériques dans le Registre.  
  
```  
BOOL WriteSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à définir.  
  
 [in] `nValue`  
 Les données à écrire dans le Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
 Si la clé spécifiée par `lpszEntry` n’existe pas, cette méthode crée.  
  
##  <a name="a-namewritesectionobjecta--cwinappexwritesectionobject"></a><a name="writesectionobject"></a>CWinAppEx::WriteSectionObject  
 Écrit des données dérivées de la [CObject (classe)](../../mfc/reference/cobject-class.md) à une valeur de Registre spécifiques.  
  
```  
BOOL WriteSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient le nom de la valeur à définir.  
  
 [in] `obj`  
 Les données à stocker.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase), respectivement.  
  
 Si la valeur spécifiée par `lpszEntry` n’existe pas sous la clé de Registre spécifiée par `lpszSubSection`, cette méthode crée cette valeur.  
  
##  <a name="a-namewritesectionstringa--cwinappexwritesectionstring"></a><a name="writesectionstring"></a>CWinAppEx::WriteSectionString  
 Écrit des données de chaîne à une valeur dans le Registre.  
  
```  
BOOL WriteSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszSubSection`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [in] `lpszEntry`  
 Chaîne qui contient la valeur à définir.  
  
 [in] `lpszValue`  
 Les données de chaîne à écrire dans le Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszSubSection` paramètre n’est pas un chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase), respectivement.  
  
 Si la valeur spécifiée par `lpszEntry` n’existe pas sous `lpszSubSection`, cette méthode crée.  
  
##  <a name="a-namewritestringa--cwinappexwritestring"></a><a name="writestring"></a>CWinAppEx::WriteString  
 Écrit des données de chaîne dans le Registre.  
  
```  
BOOL WriteString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszEntry`  
 Chaîne qui contient le nom d’une clé de Registre.  
  
 [in] `lpszValue`  
 Les données à stocker.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si cette méthode a réussi ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszEntry` paramètre est le nom d’une entrée de Registre située sous la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](#getregistrybase) et [CWinAppEx::SetRegistryBase](#setregistrybase) respectivement.  
  
 Si la clé spécifiée par `lspzEntry` n’existe pas, cette méthode crée.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinApp (classe)](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager (classe)](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager (classe)](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager (classe)](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager (classe)](../../mfc/reference/cusertoolsmanager-class.md)

