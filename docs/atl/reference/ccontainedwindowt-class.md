---
title: Classe de CContainedWindowT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindow
- CContainedWindowT
- ATL.CContainedWindowT
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
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
ms.openlocfilehash: e10aa4b455696fd217f88b6eb1de2421fccda6de
ms.lasthandoff: 02/24/2017

---
# <a name="ccontainedwindowt-class"></a>Classe de CContainedWindowT
Cette classe implémente une fenêtre contenue dans un autre objet.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Paramètres  
 *TBase*  
 La classe de base de votre nouvelle classe. La classe de base par défaut est `CWindow`.  
  
 `TWinTraits`  
 Une classe de traits qui définit les styles de votre fenêtre. La valeur par défaut est `CControlWinTraits`.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) est une spécialisation de `CContainedWindowT`. Si vous souhaitez modifier la classe de base ou traits, utilisez `CContainedWindowT` directement.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Constructeur. Initialise les membres de données pour spécifier la table des messages qui traitera les messages de la relation contenant-contenu de la fenêtre.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|Crée une fenêtre.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Fournit le traitement du message par défaut.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Retourne le message actuel.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Inscrit la classe de fenêtre de la fenêtre de relation contenant-contenue.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Sous-classe une fenêtre.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Modifie le mappage de message qui est utilisé pour traiter les messages de la fenêtre de la relation contenant-contenu.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Restaure une fenêtre précédemment sous-classée.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Statique) Traite les messages envoyés à la fenêtre de relation contenant-contenue.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Identifie la table des messages qui traitera les messages de la relation contenant-contenu de la fenêtre.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Spécifie le nom d’une classe de fenêtre existante sur laquelle une nouvelle classe de fenêtre doit être basée.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pointe vers la procédure de fenêtre d'origine de la classe de fenêtre.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Pointe vers l’objet conteneur.|  
  
## <a name="remarks"></a>Remarques  
 `CContainedWindowT`implémente une fenêtre contenue dans un autre objet. `CContainedWindowT`'s utilise de procédure de fenêtre mappage d’un message dans l’objet conteneur pour diriger les messages vers les gestionnaires appropriés. Lorsque vous construisez un `CContainedWindowT` de l’objet, vous spécifiez le mappage des messages doit être utilisé.  
  
 `CContainedWindowT`permet de créer une nouvelle fenêtre en surclasser une classe de fenêtre. Le **créer** méthode enregistre tout d’abord une classe de fenêtre qui est basée sur une classe existante mais utilise `CContainedWindowT::WindowProc`. **Créer** crée ensuite une fenêtre basée sur cette nouvelle classe de fenêtre. Chaque instance de `CContainedWindowT` pouvez surclasser une classe de fenêtre différente.  
  
 `CContainedWindowT` prend également en charge le sous-classement de fenêtre. La méthode `SubclassWindow` attache une fenêtre existante à l'objet `CContainedWindowT` et remplace la procédure de fenêtre par `CContainedWindowT::WindowProc`. Chaque instance de `CContainedWindowT` peut sous-classer une fenêtre différente.  
  
> [!NOTE]
>  Des `CContainedWindowT` de l’objet, appelez **créer** ou `SubclassWindow`. Vous ne devez pas appeler les méthodes sur le même objet.  
  
 Lorsque vous utilisez la **ajouter un contrôle basé sur** option dans l’Assistant Projet ATL, l’Assistant ajoute automatiquement un `CContainedWindowT` membre de données à la classe implémentant le contrôle. L’exemple suivant montre comment la fenêtre contenue est déclarée :  
  
 [!code-cpp[NVC_ATL_Windowing&#38;](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing n °&39;](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing numéro&40;](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Pour plus d'informations sur|Voir|  
|--------------------------------|---------|  
|Création de contrôles|[ATL (didacticiel)](../../atl/active-template-library-atl-tutorial.md)|  
|Utilisation de fenêtres dans ATL|[Classes de fenêtre ATL](../../atl/atl-window-classes.md)|  
|Assistant Projet ATL|[Création d’un projet ATL](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) et les rubriques suivantes dans la[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-nameccontainedwindowta--ccontainedwindowtccontainedwindowt"></a><a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 Le constructeur initialise les membres de données.  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>Paramètres  
 `lpszClassName`  
 [in] Le nom d’une classe de fenêtre existante sur laquelle la fenêtre contenue doit être basée.  
  
 `pObject`  
 [in] Pointeur vers l’objet conteneur qui déclare la table des messages. Cette classe de l’objet doit dériver de [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Identifie la table des messages qui traitera les messages de la fenêtre de la relation contenant-contenu. La valeur par défaut, 0, spécifie la table des messages par défaut déclarée avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Pour utiliser une autre table des messages déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), transmettez `msgMapID`.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez créer une nouvelle fenêtre via [créer](#create), vous devez passer le nom d’une classe de fenêtre existante pour la `lpszClassName` paramètre. Pour obtenir un exemple, consultez la [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) vue d’ensemble.  
  
 Il existe trois constructeurs :  
  
-   Le constructeur avec trois arguments est généralement appelée.  
  
-   Le constructeur avec deux arguments utilise le nom de classe à partir de **TBase::GetWndClassName**.  
  
-   Le constructeur sans arguments est utilisé si vous souhaitez fournir les arguments ultérieurement. Vous devez fournir le nom de classe de fenêtre, objet de mappage de message et ID de mappage de message lorsque vous appelez ultérieurement **créer**.  
  
 Si vous sous-classer une fenêtre existante via [SubclassWindow](#subclasswindow), le `lpszClassName` valeur ne sera pas utilisée ; par conséquent, vous pouvez passer **NULL** pour ce paramètre.  
  
##  <a name="a-namecreatea--ccontainedwindowtcreate"></a><a name="create"></a>CContainedWindowT::Create  
 Appels [RegisterWndSuperclass](#registerwndsuperclass) pour enregistrer une classe de fenêtre qui est basée sur une classe existante mais utilise [CContainedWindowT::WindowProc](#windowproc).  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszClassName`  
 [in] Le nom d’une classe de fenêtre existante sur laquelle la fenêtre contenue doit être basée.  
  
 `pObject`  
 [in] Pointeur vers l’objet conteneur qui déclare la table des messages. Cette classe de l’objet doit dériver de [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Identifie la table des messages qui traitera les messages de la fenêtre de la relation contenant-contenu. La valeur par défaut, 0, spécifie la table des messages par défaut déclarée avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Pour utiliser une autre table des messages déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), transmettez `msgMapID`.  
  
 `hWndParent`  
 [in] Handle de la fenêtre parente ou propriétaire.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure spécifiant la position de la fenêtre. Les `RECT` peuvent être passés par le pointeur ou par référence.  
  
 `szWindowName`  
 [in] Spécifie le nom de la fenêtre. La valeur par défaut est **NULL**.  
  
 `dwStyle`  
 [in] Le style de la fenêtre. La valeur par défaut est **WS_CHILD | WS_VISIBLE**. Pour obtenir la liste des valeurs possibles, consultez la page [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwExStyle`  
 [in] Le style de fenêtre étendus. La valeur par défaut est 0, ce qui signifie qu’aucun style étendu. Pour obtenir la liste des valeurs possibles, consultez la page [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `MenuOrID`  
 [in] Pour une fenêtre enfant, l’identificateur de la fenêtre. Pour une fenêtre de niveau supérieur, un descripteur de menu de la fenêtre. La valeur par défaut est **0 u**.  
  
 `lpCreateParam`  
 [in] Pointeur vers les données de création de fenêtre. Pour une description complète, consultez la description pour le paramètre final [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, le handle de la fenêtre qui vient d’être créé ; dans le cas contraire, **NULL**.  
  
### <a name="remarks"></a>Notes  
 Le nom de classe de fenêtre existante est enregistré dans [m_lpszClassName](#m_lpszclassname). **Créer** crée ensuite une fenêtre basée sur cette nouvelle classe. La fenêtre nouvellement créée est automatiquement joint à la `CContainedWindowT` objet.  
  
> [!NOTE]
>  N’appelez pas **créer** si vous avez déjà appelé [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  Si 0 est utilisée comme valeur pour le `MenuOrID` paramètre, il doit être spécifié en tant que 0 u (valeur par défaut) pour éviter une erreur du compilateur.  
  
##  <a name="a-namedefwindowproca--ccontainedwindowtdefwindowproc"></a><a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Appelé par [WindowProc](#windowproc) pour traiter les messages non gérées par la table des messages.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `uMsg`  
 [in] Le message est envoyé à la fenêtre.  
  
 `wParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message.  
  
### <a name="remarks"></a>Notes  
 Par défaut, `DefWindowProc` appelle la [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) fonction Win32 pour envoyer les informations de message à la procédure spécifiée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
##  <a name="a-namegetcurrentmessagea--ccontainedwindowtgetcurrentmessage"></a><a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Retourne le message actuel ( **m_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le message en cours, empaqueté dans la `MSG` structure.  
  
##  <a name="a-namemdwmsgmapida--ccontainedwindowtmdwmsgmapid"></a><a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Contient l’identificateur de la table des messages en cours d’utilisation de la fenêtre de relation contenant-contenue.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Notes  
 Cette table des messages doit être déclarée dans l’objet conteneur.  
  
 La table des messages par défaut déclaré avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), est toujours identifié par zéro. Une table des messages secondaire, déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), est identifié par `msgMapID`.  
  
 `m_dwMsgMapID`est d’abord initialisée par le constructeur et peut être modifiée en appelant [SwitchMessageMap](#switchmessagemap). Pour obtenir un exemple, consultez la [vue d’ensemble de CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="a-namemlpszclassnamea--ccontainedwindowtmlpszclassname"></a><a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Spécifie le nom d’une classe de fenêtre existante.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Notes  
 Lorsque vous créez une fenêtre, [créer](#create) enregistre une nouvelle classe de fenêtre qui est basée sur cette classe existante mais utilise [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`est initialisé par le constructeur. Pour obtenir un exemple, consultez la [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) vue d’ensemble.  
  
##  <a name="a-namempfnsuperwindowproca--ccontainedwindowtmpfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Si la fenêtre de relation contenant-contenue est sous-classée, `m_pfnSuperWindowProc` pointe vers la procédure de fenêtre d’origine de la classe de fenêtre.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Notes  
 Si la fenêtre de relation contenant-contenue est superclasse, ce qui signifie qu’il est basé sur une classe de fenêtre qui modifie une classe existante, `m_pfnSuperWindowProc` pointe vers la procédure de fenêtre de la classe de fenêtre existante.  
  
 Le [DefWindowProc](#defwindowproc) méthode envoie des informations de message à la procédure de fenêtre enregistrée dans `m_pfnSuperWindowProc`.  
  
##  <a name="a-namempobjecta--ccontainedwindowtmpobject"></a><a name="m_pobject"></a>CContainedWindowT::m_pObject  
 Pointe vers l’objet contenant le `CContainedWindowT` objet.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Remarques  
 Ce conteneur, dont la classe doit dériver de [CMessageMap](../../atl/reference/cmessagemap-class.md), déclare le mappage de message utilisé par la fenêtre de relation contenant-contenue.  
  
 `m_pObject`est initialisé par le constructeur. Pour obtenir un exemple, consultez la [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) vue d’ensemble.  
  
##  <a name="a-nameregisterwndsuperclassa--ccontainedwindowtregisterwndsuperclass"></a><a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Appelé par [créer](#create) pour inscrire la classe de fenêtre de la fenêtre de relation contenant-contenue.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, un atome qui identifie la classe de fenêtre en cours d’enregistrement ; Sinon, zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette classe de fenêtre basée sur une classe existante mais utilise [CContainedWindowT::WindowProc](#windowproc). Procédure de fenêtre et de nom de la classe de fenêtre existante sont enregistrés dans [m_lpszClassName](#m_lpszclassname) et [m_pfnSuperWindowProc](#m_pfnsuperwindowproc), respectivement.  
  
##  <a name="a-namesubclasswindowa--ccontainedwindowtsubclasswindow"></a><a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 La fenêtre est identifiée par les sous-classes `hWnd` et l’attache à le `CContainedWindowT` objet.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de la fenêtre sous-classée.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la fenêtre a été sous-classé ; sinon, **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 La fenêtre sous-classée utilise désormais [CContainedWindowT::WindowProc](#windowproc). La procédure de fenêtre d’origine est enregistrée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  N’appelez pas `SubclassWindow` si vous avez déjà appelé [créer](#create).  
  
##  <a name="a-nameswitchmessagemapa--ccontainedwindowtswitchmessagemap"></a><a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Modifie le mappage des messages permet de traiter les messages de la fenêtre de la relation contenant-contenu.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMsgMapID`  
 [in] Identificateur de la carte de message. Pour utiliser le mappage de message par défaut déclaré avec [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), transférez la valeur zéro. Pour utiliser une autre table des messages déclarée avec [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), transmettez `msgMapID`.  
  
### <a name="remarks"></a>Remarques  
 La table des messages doit être définie dans l’objet conteneur.  
  
 Initialement, vous spécifiez l’identificateur de carte dans le constructeur.  
  
##  <a name="a-nameunsubclasswindowa--ccontainedwindowtunsubclasswindow"></a><a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Détache la fenêtre sous-classé à partir de la `CContainedWindowT` de l’objet et restaure la procédure de fenêtre d’origine, enregistrée dans [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bForce`  
 [in] La valeur **TRUE** pour forcer la procédure de fenêtre d’origine pour être restaurée même si la procédure de fenêtre pour ce `CContainedWindowT` objet n’est pas actuellement actif. Si `bForce` a **FALSE** et la procédure de fenêtre pour ce `CContainedWindowT` objet n’est pas actif, la procédure de fenêtre d’origine ne seront pas restaurée.  
  
### <a name="return-value"></a>Valeur de retour  
 Handle de la fenêtre précédemment sous-classée. Si `bForce` a **FALSE** et la procédure de fenêtre pour ce `CContainedWindowT` objet n’est pas actif, retourne **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode uniquement si vous souhaitez restaurer la procédure de fenêtre d’origine avant la destruction de la fenêtre. Dans le cas contraire, [WindowProc](#windowproc) fera automatiquement lorsque la fenêtre est détruite.  
  
##  <a name="a-namewindowproca--ccontainedwindowtwindowproc"></a><a name="windowproc"></a>CContainedWindowT::WindowProc  
 Cette méthode statique implémente la procédure de fenêtre.  
  
```
static LRESULT CALLBACK WindowProc(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de la fenêtre.  
  
 `uMsg`  
 [in] Le message est envoyé à la fenêtre.  
  
 `wParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
 `lParam`  
 [in] Spécifique au message des informations supplémentaires.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat du traitement du message.  
  
### <a name="remarks"></a>Remarques  
 `WindowProc`dirige les messages vers la table des messages identifiés par [m_dwMsgMapID](#m_dwmsgmapid). Si nécessaire, `WindowProc` appelle [DefWindowProc](#defwindowproc) pour le traitement des messages supplémentaires.  
  
## <a name="see-also"></a>Voir aussi  
 [CWindow (classe)](../../atl/reference/cwindow-class.md)   
 [CWindowImpl (classe)](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap (classe)](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

