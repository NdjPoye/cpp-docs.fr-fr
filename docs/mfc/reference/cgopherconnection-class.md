---
title: "Classe d’objet CGopherConnection | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherConnection
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- Internet server, gopher
- connecting to servers, gopher servers
- protocols, gopher
- services, gopher
- CGopherConnection class
- gopher protocol
- gopher server
- connecting to servers
- Internet connections, gopher
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
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
ms.openlocfilehash: 6267dd226e87e5bf64faa7225e49d9a99af93e3e
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherconnection-class"></a>Classe d’objet CGopherConnection
Gère votre connexion à un serveur Internet Gopher.  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres sont déconseillées, car ils ne fonctionnent pas sur la plate-forme Windows XP, mais ils continueront à fonctionner sur des plateformes antérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Construit un objet `CGopherConnection`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Crée un [objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md) objet pour rechercher des fichiers sur un serveur gopher.|  
|[CGopherConnection::GetAttribute](#getattribute)|Récupère les informations d’attribut sur l’objet gopher.|  
|[CGopherConnection::OpenFile](#openfile)|Ouvre un fichier gopher.|  
  
## <a name="remarks"></a>Remarques  
 Le service gopher est un des trois services Internet reconnus par les classes WinInet MFC.  
  
 La classe `CGopherConnection` contient un constructeur et trois fonctions membres supplémentaires qui gèrent le service gopher : [OpenFile](#openfile), [CreateLocator](#createlocator), et [GetAttribute](#getattribute).  
  
 Pour communiquer avec un serveur Internet gopher, vous devez d’abord créer une instance de [CInternetSession](../../mfc/reference/cinternetsession-class.md), puis appelez [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), qui crée la `CGopherConnection` de l’objet et retourne un pointeur vers elle. Vous ne créez jamais un `CGopherConnection` directement l’objet.  
  
 Pour en savoir plus sur le `CGopherConnection` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md). Pour plus d’informations sur les deux autres prises en charge des services Internet, FTP et HTTP voir les classes [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) et [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="a-namecgopherconnectiona--cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopherConnection::CGopherConnection  
 Cette fonction membre est appelée pour construire un `CGopherConnection` objet.  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSession`  
 Un pointeur vers le [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet.  
  
 `hConnected`  
 Handle Windows de la session Internet.  
  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur FTP.  
  
 `dwContext`  
 L’identificateur de contexte pour l’opération. `dwContext`identifie les informations d’état de l’opération retournées par [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). La valeur par défaut est défini sur 1. Toutefois, vous pouvez affecter explicitement un ID de contexte pour l’opération. L’objet et tout travail qu’elle effectue est associées à cet ID de contexte.  
  
 `pstrUserName`  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le nom de l’utilisateur pour se connecter. Si **NULL**, la valeur par défaut est anonyme.  
  
 `pstrPassword`  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie le mot de passe à utiliser pour se connecter. Si les deux `pstrPassword` et `pstrUserName` sont **NULL**, le mot de passe anonyme par défaut est le nom d’utilisateur par courrier électronique. Si `pstrPassword` est **NULL** (ou une chaîne vide), mais `pstrUserName` n’est pas **NULL**, un mot de passe vierge est utilisé. Le tableau suivant décrit le comportement pour les quatre paramètres possibles de `pstrUserName` et `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|Nom d’utilisateur est envoyé au serveur FTP|Mot de passe envoyé au serveur FTP|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** ou « »|**NULL** ou « »|« anonyme »|Nom de l’utilisateur par courrier électronique|  
|Non- **NULL** chaîne|**NULL** ou « »|`pstrUserName`|" "|  
|**NULL** non **NULL** chaîne|**ERREUR**|**ERREUR**||  
|Non- **NULL** chaîne|Non- **NULL** chaîne|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Numéro qui identifie le port TCP/IP à utiliser sur le serveur.  
  
### <a name="remarks"></a>Remarques  
 Vous ne créez jamais un `CGopherConnection` directement. Au lieu de cela, appelez [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), ce qui crée un `CGopherConnection` de l’objet et retourne un pointeur vers elle.  
  
##  <a name="a-namecreatelocatora--cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopherConnection::CreateLocator  
 Appelez cette fonction membre pour créer un localisateur gopher pour trouver ou identifier un fichier sur un serveur gopher.  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrDisplayString`  
 Pointeur vers une chaîne contenant le nom du document de gopher ou du répertoire doit être récupéré. Si le `pstrDisplayString` paramètre est **NULL**, le répertoire par défaut pour le serveur gopher est retourné.  
  
 `pstrSelectorString`  
 Pointeur vers la chaîne de sélecteur à envoyer au serveur gopher afin de récupérer un élément. `pstrSelectorString`peut être **NULL**.  
  
 *dwGopherType*  
 Spécifie si `pstrSelectorString` fait référence à un répertoire ou un document, et si la demande est gopher ou gopher +. Consultez les attributs de la structure [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pstrLocator`  
 Pointeur vers une chaîne qui identifie le fichier à ouvrir. En général, cette chaîne est retournée à partir d’un appel à [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Pointeur vers une chaîne contenant le nom de serveur gopher.  
  
 `nPort`  
 Le numéro qui identifie le port Internet pour cette connexion.  
  
### <a name="return-value"></a>Valeur de retour  
 A [objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 La version de la fonction membre statique, vous devez spécifier un serveur, tandis que la version non statique utilise le nom du serveur à partir de l’objet de connexion.  
  
 Pour récupérer des informations à partir d’un serveur gopher, une application doit d’abord obtenir une adresse gopher. L’application doit alors considère que le localisateur un jeton opaque (autrement dit, l’application peut utiliser la recherche, mais pas directement manipuler ou comparer). Normalement, l’application utilise la recherche pour les appels à la [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) fonction membre pour récupérer une information spécifique.  
  
##  <a name="a-namegetattributea--cgopherconnectiongetattribute"></a><a name="getattribute"></a>CGopherConnection::GetAttribute  
 Appelez cette fonction membre pour récupérer des informations sur un élément à partir du serveur gopher.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Paramètres  
 `refLocator`  
 Une référence à un [objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md) objet.  
  
 *strRequestedAttributes*  
 Une chaîne délimitée en spécifiant les noms des attributs requis.  
  
 `strResult`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) qui reçoit le type de recherche.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
##  <a name="a-nameopenfilea--cgopherconnectionopenfile"></a><a name="openfile"></a>CGopherConnection::OpenFile  
 Appelez cette fonction membre pour ouvrir un fichier sur un serveur gopher.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `refLocator`  
 Une référence à un [objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md) objet.  
  
 `dwFlags`  
 N’importe quelle combinaison d’indicateurs de INTERNET_FLAG_. Consultez la page [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) pour plus d’informations sur INTERNET_FLAG_\* indicateurs.  
  
 `pstrView`  
 Pointeur vers une chaîne d’affichage des fichiers. Si plusieurs vues du fichier existent sur le serveur, ce paramètre spécifie la mode fichier à ouvrir. Si `pstrView` est **NULL**, l’affichage du fichier par défaut est utilisé.  
  
 `dwContext`  
 L’ID de contexte pour le fichier ouvert. Consultez la page **remarques** pour plus d’informations sur `dwContext`.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [CGopherFile](../../mfc/reference/cgopherfile-class.md) objet doit être ouvert.  
  
### <a name="remarks"></a>Notes  
 Remplacer le `dwContext` par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est associé à cette opération spécifique de la `CGopherConnection` objet créé par son [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet. La valeur est retournée à [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’opération à laquelle elle est identifiée. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
## <a name="see-also"></a>Voir aussi  
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFtpConnection (classe)](../../mfc/reference/cftpconnection-class.md)   
 [Classe d’objet CHttpConnection](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)   
 [Classe d’objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile (classe)](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession (classe)](../../mfc/reference/cinternetsession-class.md)

