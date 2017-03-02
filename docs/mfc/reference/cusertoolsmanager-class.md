---
title: Classe de CUserToolsManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserToolsManager
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager class
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
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
ms.openlocfilehash: 0b82adf0f9eba5ee334ada2c169546f27894c1dd
ms.lasthandoff: 02/24/2017

---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager (classe)
Gère la collection de [CUserTool classe](../../mfc/reference/cusertool-class.md) objets dans une application. Un outil utilisateur est un élément de menu qui exécute une application externe. L'objet `CUserToolsManager` permet à l'utilisateur ou au développeur d'ajouter de nouveaux outils utilisateur à l'application. Il prend en charge l'exécution des commandes associées aux outils utilisateur. En outre, il stocke des informations sur les outils utilisateur dans le Registre Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|Construit un objet `CUserToolsManager`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|Crée un nouvel outil de l’utilisateur.|  
|[CUserToolsManager::FindTool](#findtool)|Retourne le pointeur vers le `CMFCUserTool` objet qui est associé à un ID de commande spécifié.|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|Retourne l’ID de ressource qui est associé à la **Arguments** menu sur le **outils** onglet de la **personnaliser** boîte de dialogue.|  
|[CUserToolsManager::GetDefExt](#getdefext)|Renvoie l’extension par défaut qui le **ouvrir le fichier** boîte de dialogue ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) utilise dans les **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.|  
|[CUserToolsManager::GetFilter](#getfilter)|Retourne le filtre de fichiers qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|Retourne l’ID de ressource qui est associé à la **répertoire Initial** menu sur le **outils** onglet de la **personnaliser** boîte de dialogue.|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|Retourne le nombre maximal d’outils utilisateur qui peuvent être alloués dans l’application.|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|Retourne l’ID de commande de l’espace réservé d’élément menu pour les outils de l’utilisateur.|  
|[CUserToolsManager::GetUserTools](#getusertools)|Retourne une référence à la liste des outils de l’utilisateur.|  
|[CUserToolsManager::InvokeTool](#invoketool)|Exécute une application associée à l’outil utilisateur qui possède un ID de commande spécifié.|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|Détermine si un ID de commande est associé à un outil utilisateur.|  
|[CUserToolsManager::LoadState](#loadstate)|Charge les informations sur les outils utilisateur à partir du Registre Windows.|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|Déplace l’outil utilisateur spécifié vers le bas dans la liste des outils de l’utilisateur.|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|Monter l’outil utilisateur spécifié dans la liste des outils de l’utilisateur.|  
|[CUserToolsManager::RemoveTool](#removetool)|Supprime l’outil utilisateur spécifié à partir de l’application.|  
|[CUserToolsManager::SaveState](#savestate)|Stocke les informations sur les outils utilisateur dans le Registre Windows.|  
|[CUserToolsManager::SetDefExt](#setdefext)|Spécifie l’extension par défaut qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.|  
|[CUserToolsManager::SetFilter](#setfilter)|Spécifie le fichier de filtre qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.|  
  
## <a name="remarks"></a>Notes  
 Pour intégrer les outils utilisateur dans votre application, vous devez :  
  
 1. Réserver un élément de menu et d’un ID de commande associée à une entrée de menu outil utilisateur.  
  
 2. Réservez un ID de commande séquentiel pour chaque outil utilisateur un utilisateur peut définir dans votre application.  
  
 3. Appelez le [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) méthode et fournir les paramètres suivants : dernier ID de commande outil utilisateur, premier ID de commande d’outil utilisateur et ID de commande de menu  
  
 Il doit y avoir qu’un seul global `CUserToolsManager` objet par application.  
  
 Pour obtenir un exemple d’outils de l’utilisateur, consultez l’exemple de projet VisualStudioDemo.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment récupérer une référence à un `CUserToolsManager` objet et comment créer de nouveaux outils utilisateur. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#38;](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxusertoolsmanager.h  
  
##  <a name="a-namecreatenewtoola--cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 Crée un nouvel outil de l’utilisateur.  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’outil utilisateur nouvellement créé, ou `NULL` si le nombre d’outils de l’utilisateur a dépassé la valeur maximale. Le type retourné est le même que le type qui est passé à `CWinAppEx::EnableUserTools` comme le `pToolRTC` paramètre.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode recherche le premier ID de commande de menu disponibles dans la plage qui est fournie dans l’appel à [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) et attribue l’outil utilisateur ce code.  
  
 La méthode échoue si le nombre d’outils a atteint le maximum. Cela se produit lorsque tous les ID de commande dans la plage sont attribués à des outils de l’utilisateur. Vous pouvez récupérer le nombre maximal d’outils en appelant [CUserToolsManager::GetMaxTools](#getmaxtools). Vous pouvez accéder à la liste des outils en appelant le [CUserToolsManager::GetUserTools](#getusertools) (méthode).  
  
##  <a name="a-namecusertoolsmanagera--cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 Construit un objet `CUserToolsManager`. Chaque application doit avoir au plus un responsable d’outils utilisateur.  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdToolsDummy`  
 Entier non signé par le framework comme espace réservé pour l’ID de commande du menu outils utilisateur.  
  
 [in] `uiCmdFirst`  
 L’ID de commande pour la première commande de l’outil utilisateur.  
  
 [in] `uiCmdLast`  
 L’ID de commande pour la dernière commande d’outil utilisateur.  
  
 [in] `pToolRTC`  
 La classe qui [CUserToolsManager::CreateNewTool](#createnewtool) crée. À l’aide de cette classe, vous pouvez utiliser un type dérivé de [CUserTool classe](../../mfc/reference/cusertool-class.md) au lieu de l’implémentation par défaut.  
  
 [in] `uArgMenuID`  
 L’ID de ressource de menu du menu contextuel arguments.  
  
 [in] `uInitDirMenuID`  
 L’ID de ressource de menu du menu contextuel répertoire initial.  
  
### <a name="remarks"></a>Remarques  
 N’appelez pas ce constructeur. Au lieu de cela, appelez [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) pour activer les outils utilisateur, puis appelez [CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) pour obtenir un pointeur vers le `CUserToolsManager`. Pour plus d’informations, consultez [outils définis par l’utilisateur](../../mfc/user-defined-tools.md).  
  
##  <a name="a-namefindtoola--cusertoolsmanagerfindtool"></a><a name="findtool"></a>CUserToolsManager::FindTool  
 Retourne le pointeur vers le [CUserTool classe](../../mfc/reference/cusertool-class.md) objet qui est associé à un ID de commande spécifié.  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdId`  
 Un identificateur de commande de menu.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CUserTool classe](../../mfc/reference/cusertool-class.md) ou `CUserTool`-objet dérivé si succès ; sinon `NULL`.  
  
### <a name="remarks"></a>Notes  
 Lors de la `FindTool` est réussie, le type retourné est le même que le type de la `pToolRTC` paramètre [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="a-namegetargumentsmenuida--cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 Retourne l’ID de ressource qui est associé à la **Arguments** menu sur le **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’identificateur d’une ressource de menu.  
  
### <a name="remarks"></a>Notes  
 Le `uArgMenuID` paramètre de [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) Spécifie l’ID de la ressource.  
  
##  <a name="a-namegetdefexta--cusertoolsmanagergetdefext"></a><a name="getdefext"></a>CUserToolsManager::GetDefExt  
 Renvoie l’extension par défaut qui le **ouvrir le fichier** boîte de dialogue ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) utilise dans les **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la `CString` objet qui contient l’extension.  
  
##  <a name="a-namegetfiltera--cusertoolsmanagergetfilter"></a><a name="getfilter"></a>CUserToolsManager::GetFilter  
 Retourne le filtre de fichiers qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la `CString` objet qui contient le filtre.  
  
##  <a name="a-namegetinitialdirmenuida--cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 Retourne l’ID de ressource qui est associé à la **répertoire Initial** menu sur le **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un identificateur de ressource de menu.  
  
### <a name="remarks"></a>Remarques  
 L’ID retourné est spécifié dans le `uInitDirMenuID` paramètre de [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="a-namegetmaxtoolsa--cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 Retourne le nombre maximal d’outils utilisateur qui peuvent être alloués dans l’application.  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal d’outils utilisateur qui peuvent être alloués.  
  
### <a name="remarks"></a>Notes  
 Appelez cette méthode pour récupérer le nombre maximal d’outils qui peuvent être alloués dans l’application. Ce nombre est le nombre d’ID dans la plage comprise entre le `uiCmdFirst` via la `uiCmdLast` les paramètres que vous passez à [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools).  
  
##  <a name="a-namegettoolsentrycmda--cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 Retourne l’ID de commande de l’espace réservé d’élément menu pour les outils de l’utilisateur.  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de l’espace réservé.  
  
### <a name="remarks"></a>Notes  
 Pour activer les outils de l’utilisateur, vous appelez [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools). Le `uiCmdToolsDummy` paramètre spécifie l’ID de commande de la commande d’entrée outils. Cette méthode retourne l’ID de commande de saisie des outils. Partout où cet ID est utilisé dans un menu, elle est remplacée par la liste des outils de l’utilisateur lorsque le menu s’affiche.  
  
##  <a name="a-namegetusertoolsa--cusertoolsmanagergetusertools"></a><a name="getusertools"></a>CUserToolsManager::GetUserTools  
 Retourne une référence à la liste des outils de l’utilisateur.  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence const vers un [CObList classe](../../mfc/reference/coblist-class.md) objet qui contient une liste d’outils de l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette méthode pour récupérer la liste des utilisateurs des outils fournis par le [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) objet conserve. Chaque outil utilisateur est représenté par un objet de type [CUserTool classe](../../mfc/reference/cusertool-class.md) ou un type dérivé `CUserTool`. Le type est spécifié par le `pToolRTC` paramètre lorsque vous appelez [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) pour permettre aux outils de l’utilisateur.  
  
##  <a name="a-nameinvoketoola--cusertoolsmanagerinvoketool"></a><a name="invoketool"></a>CUserToolsManager::InvokeTool  
 Exécute une application associée à l’outil utilisateur qui possède un ID de commande spécifié.  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdId`  
 L’ID de commande de menu associé à l’outil.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la commande associée outil utilisateur a été exécutée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette méthode pour exécuter une application associée à l’utilisateur d’outils qui a l’ID de commande spécifié par `uiCmdId`.  
  
##  <a name="a-nameisusertoolcmda--cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 Détermine si un ID de commande est associé à un outil utilisateur.  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiCmdId`  
 ID de commande de l’élément de menu.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’ID de commande donné est associé à un outil utilisateur ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette méthode vérifie si l’ID de commande donné est dans la plage d’ID de commande. Vous spécifiez la plage lorsque vous appelez [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) pour permettre aux outils de l’utilisateur.  
  
##  <a name="a-nameloadstatea--cusertoolsmanagerloadstate"></a><a name="loadstate"></a>CUserToolsManager::LoadState  
 Charge les informations sur les outils utilisateur à partir du Registre Windows.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Le chemin d’accès de la clé de Registre Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’état a été chargé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette méthode charge l’état de le `CUserToolsManager` l’objet à partir du Registre Windows.  
  
 En règle générale, vous n’appelez pas cette méthode directement. [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate) appelle dans le cadre du processus d’initialisation d’espace de travail.  
  
##  <a name="a-namemovetooldowna--cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 Déplace l’outil utilisateur spécifié vers le bas dans la liste des outils de l’utilisateur.  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pTool`  
 Spécifie l’outil utilisateur à déplacer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’outil a été déplacé vers le bas avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 La méthode échoue si l’outil qui le `pTool` Spécifie n’est pas dans la liste interne ou si l’outil est le dernier dans la liste.  
  
##  <a name="a-namemovetoolupa--cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 Monter l’outil utilisateur spécifié dans la liste des outils de l’utilisateur.  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pTool`  
 Spécifie l’outil utilisateur à déplacer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’outil a été déplacé vers le haut avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 La méthode échoue si l’outil qui le `pTool` paramètre spécifie n’est pas dans la liste interne ou si l’outil est le premier élément d’outil dans la liste.  
  
##  <a name="a-nameremovetoola--cusertoolsmanagerremovetool"></a><a name="removetool"></a>CUserToolsManager::RemoveTool  
 Supprime l’outil utilisateur spécifié à partir de l’application.  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `pTool`  
 Pointeur vers un outil utilisateur à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’outil a été supprimé. Sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Si l’outil a été supprimé, cette méthode supprime `pTool`.  
  
##  <a name="a-namesavestatea--cusertoolsmanagersavestate"></a><a name="savestate"></a>CUserToolsManager::SaveState  
 Stocke les informations sur les outils utilisateur dans le Registre Windows.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Un chemin d’accès à la clé de Registre Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’état a été enregistré avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 La méthode stocke l’état actuel de le `CUserToolsManager` l’objet dans le Registre Windows.  
  
 En règle générale, il est inutile d’appeler cette méthode directement, [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate) appelle automatiquement dans le cadre du processus de sérialisation d’espace de travail de l’application.  
  
##  <a name="a-namesetdefexta--cusertoolsmanagersetdefext"></a><a name="setdefext"></a>CUserToolsManager::SetDefExt  
 Spécifie l’extension par défaut qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `strDefExt`  
 Une chaîne de texte qui contient l’extension de nom de fichier par défaut.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour spécifier une extension de nom de fichier par défaut dans le **ouvrir le fichier** boîte de dialogue qui s’affiche lorsque l’utilisateur sélectionne une application à associer à l’outil. La valeur par défaut est « exe ».  
  
##  <a name="a-namesetfiltera--cusertoolsmanagersetfilter"></a><a name="setfilter"></a>CUserToolsManager::SetFilter  
 Spécifie le fichier de filtre qui le **ouvrir le fichier** boîte de dialogue ( [classe CFileDialog](../../mfc/reference/cfiledialog-class.md)) utilise dans le **commande** de la **outils** onglet de la **personnaliser** boîte de dialogue.  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `strFilter`  
 Spécifie le filtre.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)   
 [CUserTool (classe)](../../mfc/reference/cusertool-class.md)

