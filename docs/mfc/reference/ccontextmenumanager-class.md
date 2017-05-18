---
title: Classe de CContextMenuManager | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager class
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
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
ms.openlocfilehash: fab322d0c60b33454504620170d9c77a98401ec8
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager (classe)
Le `CContextMenuManager` objet gère les menus contextuels, également connu sous les menus contextuels.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Construit un objet `CContextMenuManager`.|  
|`CContextMenuManager::~CContextMenuManager`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Ajoute un menu contextuel.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Retourne un handle vers le menu associé à l’ID de ressource fourni.|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Retourne un handle vers le menu qui correspond au nom de menu fournis.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Retourne une liste de noms de menu.|  
|[CContextMenuManager::LoadState](#loadstate)|Charge les menus contextuels stockées dans le Registre Windows.|  
|[CContextMenuManager::ResetState](#resetstate)|Efface les menus contextuels à partir du Gestionnaire de menu contextuel.|  
|[CContextMenuManager::SaveState](#savestate)|Enregistre les menus contextuels dans le Registre Windows.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Contrôle si le `CContextMenuManager` ferme le menu contextuel active lorsqu’il affiche un menu contextuel.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Affiche le menu contextuel spécifié.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Affiche le menu contextuel spécifié. Retourne l’index de la commande de menu sélectionné.|  
  
## <a name="remarks"></a>Remarques  
 `CContextMenuManager`gère les menus contextuels et permet de s’assurer qu’ils ont une apparence cohérente.  
  
 Vous ne devez pas créer un `CContextMenuManager` de l’objet manuellement. L’infrastructure de votre application crée le `CContextMenuManager` objet. Toutefois, vous devez appeler [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) lorsque votre application est initialisée. Après l’initialisation du Gestionnaire de contexte, utilisez la méthode [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) pour obtenir un pointeur vers le Gestionnaire de contexte de votre application.  
  
 Vous pouvez créer des menus contextuels au moment de l’exécution en appelant `AddMenu`. Si vous souhaitez afficher le menu sans intervention de l’utilisateur destinataire première, appelez `ShowPopupMenu`. `TrackPopupMenu`est utilisé lorsque vous souhaitez créer un menu et attendez que l’entrée d’utilisateur. `TrackPopupMenu`Retourne l’index de la commande sélectionnée ou 0 si l’utilisateur s’est arrêté sans rien sélectionner.  
  
 Le `CContextMenuManager` peut également enregistrer et charger son état dans le Registre Windows.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment ajouter un menu à un `CContextMenuManager` objet et comment ne pas fermer le menu contextuel actif lorsque le `CContextMenuManager` objet affiche un menu contextuel. Cet extrait de code fait partie de la [les exemples de Pages personnalisées](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages n °&4;](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 Ajoute un menu contextuel pour le [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiMenuNameResId`  
 Un ID de ressource pour une chaîne qui contient le nom du nouveau menu.  
  
 [in] `uiMenuResId`  
 L’ID de ressource de menu.  
  
 [in] `lpszName`  
 Chaîne qui contient le nom du nouveau menu.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; 0 si la méthode échoue.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode échoue si `uiMenuResId` n’est pas valide ou si un autre menu portant le même nom existe déjà dans le `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Construit un [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) objet.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Remarques  
 Dans la plupart des cas, ne créez pas une `CContextMenuManager` manuellement. L’infrastructure de votre application crée le `CContextMenuManager` objet. Vous devez appeler [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) pendant l’initialisation de votre application. Pour obtenir un pointeur vers le Gestionnaire de contexte, appelez [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 Retourne un handle vers le menu associé à un ID de ressource donné.  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nMenuResId`  
 L’ID de ressource pour le menu.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle vers le menu associé ou `NULL` si le menu est introuvable.  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 Retourne un handle vers un menu spécifique.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszName`  
 Chaîne qui contient le nom du menu à récupérer.  
  
 [out] `puiOrigResID`  
 Pointeur vers `UINT`. Ce paramètre contient l’ID de ressource du menu spécifié, si trouvé.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle vers le menu qui correspond au nom spécifié par `lpszName`. `NULL`s’il n’existe aucun menu appelé `lpszName`.  
  
### <a name="remarks"></a>Remarques  
 Si cette méthode trouve un menu qui correspond à `lpszName`, `GetMenuByName` stocke l’ID de ressource de menu dans le paramètre `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Retourne la liste des noms de menu ajouté à la [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `listOfNames`  
 Une référence à un [CStringList](../../mfc/reference/cstringlist-class.md) paramètre. Cette méthode écrit la liste des noms de menu pour ce paramètre.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 Charge les informations associées à la [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md) à partir du Registre Windows.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszProfileName` paramètre n’est pas le chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) et [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) respectivement.  
  
 Utilisez la méthode [CContextMenuManager::SaveState](#savestate) pour enregistrer les menus contextuels dans le Registre.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Efface tous les éléments à partir du menu contextuel associé à la [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la méthode a réussi ; `FALSE` si une défaillance se produit.  
  
### <a name="remarks"></a>Notes  
 Cette méthode efface les menus contextuels et les supprime de la `CContextMenuManager`.  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 Enregistre les informations associées à la [CContextMenuManager classe](../../mfc/reference/ccontextmenumanager-class.md) dans le Registre Windows.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszProfileName`  
 Chaîne qui contient le chemin d’accès relatif d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszProfileName` paramètre n’est pas le chemin d’accès absolu pour une entrée de Registre. Il est un chemin d’accès relatif qui est ajouté à la fin de la clé de Registre par défaut pour votre application. Pour obtenir ou définir la clé de Registre par défaut, utilisez les méthodes [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) et [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) respectivement.  
  
 Utilisez la méthode [CContextMenuManager::LoadState](#loadstate) pour charger les menus contextuels à partir du Registre.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Contrôle si les [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) ferme le menu contextuel actif lorsqu’il affiche un menu contextuel.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bSet`  
 Un paramètre booléen qui détermine s’il faut fermer le menu contextuel actif. Valeur `TRUE` indique le menu contextuel actif n’est pas fermé. `FALSE`Indique que la liste déroulante active est fermée.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, le `CContextMenuManager` ferme le menu contextuel actif.  
  
##  <a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu  
 Affiche le menu contextuel spécifié.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiMenuResId`  
 L’ID de ressource du menu affiche cette méthode.  
  
 [in] `x`  
 Le décalage pour le menu contextuel en coordonnées clientes à l’horizontale.  
  
 [in] `y`  
 Le décalage vertical pour le menu contextuel dans les coordonnées clientes  
  
 [in] `pWndOwner`  
 Pointeur vers la fenêtre parent du menu contextuel.  
  
 [in] `bOwnMessage`  
 Un paramètre booléen qui indique comment les messages sont routés. Si `bOwnMessage` est `FALSE`, le routage de MFC standard est utilisé. Dans le cas contraire, `pWndOwner` reçoit les messages.  
  
 [in] `hmenuPopup`  
 Le handle du menu affiche cette méthode.  
  
 [in] `bAutoDestroy`  
 Un paramètre booléen qui indique si les menus sont automatiquement détruits.  
  
 [in] `bRightAlign`  
 Un paramètre booléen qui indique la manière dont les éléments de menu sont alignées. Si `bRightAlign` est `TRUE`, le menu est aligné à droite pour l’ordre de lecture de droite à gauche.  
  
### <a name="return-value"></a>Valeur de retour  
 La première surcharge de méthode retourne zéro si la méthode affiche le menu avec succès ; sinon 0. La deuxième surcharge de méthode retourne un pointeur vers [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) si le menu contextuel s’affiche correctement, sinon `NULL`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est semblable à la méthode [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) dans la mesure où les deux méthodes d’affichent un menu contextuel. Toutefois, `TrackPopupMenu` retourne l’index de la commande de menu sélectionné.  
  
 Si le paramètre `bAutoDestroy` est `FALSE`, vous devez appeler manuellement la `DestroyMenu` méthode pour libérer des ressources mémoire. L’implémentation par défaut de `ShowPopupMenu` n’utilise pas le paramètre `bAutoDestroy`. Il est fourni pour une utilisation ultérieure ou pour les classes personnalisées dérivées de la `CContextMenuManager` classe.  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 Affiche le menu contextuel spécifié et retourne l’index de la commande de menu contextuel sélectionné.  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hmenuPopup`  
 Le handle du menu contextuel qui affiche cette méthode.  
  
 [in] `x`  
 Le décalage pour le menu contextuel en coordonnées clientes à l’horizontale.  
  
 [in] `y`  
 Vertical de décalage pour le menu contextuel dans les coordonnées clientes.  
  
 [in] `pWndOwner`  
 Pointeur vers la fenêtre parent du menu contextuel.  
  
 [in] `bRightAlign`  
 Un paramètre booléen qui indique l’alignement des éléments de menu. Si `bRightAlign` est `TRUE`, le menu est aligné à droite pour l’ordre de lecture de droite à gauche. Si `bRightAlign` est `FALSE`, le menu est aligné à gauche de l’ordre de lecture de gauche à droite.  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de commande de menu de la commande que l’utilisateur choisit ; 0 si l’utilisateur ferme le menu contextuel sans sélectionner une commande de menu.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode fonctionne comme un appel modal pour afficher un menu contextuel. L’application ne continuera pas à la ligne suivante dans le code jusqu'à ce que l’utilisateur ferme le menu contextuel ou sélectionne une commande. Une autre méthode que vous pouvez utiliser pour afficher un menu contextuel est [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Cette méthode n’est pas un appel modal et ne retournera pas l’ID de la commande sélectionnée.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)

