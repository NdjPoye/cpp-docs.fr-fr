---
title: Classe de CInternetSession | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
dev_langs:
- C++
helpviewer_keywords:
- CInternetSession class
- Internet sessions
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
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
ms.openlocfilehash: caec3ae416dc82d49fc0051f0d9d1d2e021e0ba5
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetsession-class"></a>CInternetSession (classe)
Crée et initialise une ou plusieurs sessions Internet simultanées et, si nécessaire, décrit votre connexion à un serveur proxy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CInternetSession : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetSession::CInternetSession](#cinternetsession)|Construit un objet `CInternetSession`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetSession::Close](#close)|Ferme la connexion à Internet lors de la fin de la session Internet.|  
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Établit une routine de rappel d’état.|  
|[CInternetSession::GetContext](#getcontext)|Ferme la connexion à Internet lors de la fin de la session Internet.|  
|[CInternetSession::GetCookie](#getcookie)|Retourne les cookies pour l’URL spécifiée et tous les parents de son URL.|  
|[CInternetSession::GetCookieLength](#getcookielength)|Récupère la variable en spécifiant la longueur du cookie stocké dans la mémoire tampon.|  
|[CInternetSession::GetFtpConnection](#getftpconnection)|Ouvre une session FTP avec un serveur. L’utilisateur se connecte.|  
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Ouvre un serveur gopher pour une application qui tente d’ouvrir une connexion.|  
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Ouvre un serveur HTTP pour une application qui tente d’ouvrir une connexion.|  
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Met à jour l’état d’une opération lorsque le rappel d’état est activé.|  
|[CInternetSession::OpenURL](#openurl)|Analyse et ouvre une URL.|  
|[CInternetSession::SetCookie](#setcookie)|Définit un cookie pour l’URL spécifiée.|  
|[CInternetSession::SetOption](#setoption)|Définit les options pour la session Internet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Handle de la session Internet.|  
  
## <a name="remarks"></a>Remarques  
 Si votre connexion Internet doit être conservée pour la durée d’une application, vous pouvez créer un `CInternetSession` membre de la classe [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Une fois que vous avez établi une session Internet, vous pouvez appeler [OpenURL](#openurl). `CInternetSession`analyse ensuite l’URL pour vous en appelant la fonction globale [AfxParseURL](http://msdn.microsoft.com/library/505c717e-aa52-4106-8522-eedff3d9bbae). Quel que soit son type de protocole, `CInternetSession` interprète l’URL et le gère pour vous. Il peut gérer les demandes pour les fichiers locaux, identifiés par la ressource d’URL « file:// ». `OpenURL`Retourne un pointeur vers un [CStdioFile](../../mfc/reference/cstdiofile-class.md) objet si le nom que vous passez est un fichier local.  
  
 Si vous ouvrez une URL sur un serveur Internet en utilisant `OpenURL`, vous pouvez lire des informations à partir du site. Si vous souhaitez effectuer des actions de service spécifique (par exemple, HTTP, FTP ou gopher) sur les fichiers situés sur un serveur, vous devez établir la connexion appropriée à ce serveur. Pour ouvrir un type particulier de connexion directe à un service particulier, utilisez une des fonctions membres suivantes :  
  
- [GetGopherConnection](#getgopherconnection) pour ouvrir une connexion à un service gopher.  
  
- [GetHttpConnection](#gethttpconnection) pour ouvrir une connexion à un service HTTP.  
  
- [GetFtpConnection](#getftpconnection) pour ouvrir une connexion à un service FTP.  
  
 [SetOption](#setoption) vous permet de définir les options de requête de votre session, telles que les valeurs de délai d’attente, le nombre de nouvelles tentatives, et ainsi de suite.  
  
 `CInternetSession`les fonctions membres [SetCookie](#setcookie), [GetCookie](#getcookie), et [GetCookieLength](#getcookielength) fournissent les moyens de gérer une base de données de cookie Win32, par le biais duquel les scripts et les serveurs de mettre à jour les informations d’état sur la station de travail.  
  
 Pour plus d’informations sur les tâches de programmation de base Internet, consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md). Pour obtenir des informations générales sur l’utilisation des classes WinInet MFC, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
> `CInternetSession`génère une [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) pour les types de service non pris en charge. Charge actuellement les seuls les types de service suivants : FTP, HTTP, gopher et fichier.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="cinternetsession"></a>CInternetSession::CInternetSession  
 Cette fonction membre est appelée quand un `CInternetSession` objet est créé.  
  
```  
CInternetSession(
    LPCTSTR pstrAgent = NULL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,  
    LPCTSTR pstrProxyName = NULL,  
    LPCTSTR pstrProxyBypass = NULL,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrAgent`  
 Pointeur vers une chaîne qui identifie le nom de l’application ou une entité d’appeler les fonctions d’Internet (par exemple, « navigateur Microsoft Internet »). Si `pstrAgent` est **NULL** (la valeur par défaut), le framework appelle la fonction globale [AfxGetAppName](application-information-and-management.md#afxgetappname), qui retourne une chaîne contenant un nom de l’application. Certains protocoles utilisent cette chaîne pour identifier votre application sur le serveur.  
  
 `dwContext`  
 L’identificateur de contexte pour l’opération. `dwContext`identifie les informations d’état de l’opération retournées par [CInternetSession::OnStatusCallback](#onstatuscallback). La valeur par défaut est défini sur 1. Toutefois, vous pouvez affecter explicitement un ID de contexte pour l’opération. L’objet et tout travail qu’elle effectue est associées à cet ID de contexte.  
  
 `dwAccessType`  
 Le type d’accès requis. Les valeurs valides, seul qui peut-être être fourni sont les suivantes :  
  
- **INTERNET_OPEN_TYPE_PRECONFIG** se connecter à l’aide de paramètres prédéfinis dans le Registre. Ce type d’accès est défini comme la valeur par défaut. Pour vous connecter via un proxy TIS, définissez `dwAccessType` à cette valeur ; vous puis configurez le Registre en conséquence.  
  
- `INTERNET_OPEN_TYPE_DIRECT`Se connecter directement à Internet.  
  
- `INTERNET_OPEN_TYPE_PROXY`Se connecter via un proxy CERN.  
  
 Pour plus d’informations sur la connexion avec différents types de proxy, consultez [les étapes dans une Application de Client FTP typique](../../mfc/steps-in-a-typical-ftp-client-application.md).  
  
 *pstrProxyName*  
 Le nom du proxy CERN préféré si `dwAccessType` est défini comme `INTERNET_OPEN_TYPE_PROXY`. La valeur par défaut est **NULL**.  
  
 *pstrProxyBypass*  
 Pointeur vers une chaîne contenant une liste facultative d’adresses du serveur. Ces adresses peuvent être ignorés lors de l’utilisation d’un accès au proxy. Si un **NULL** valeur est fournie, la liste d’exclusion est lues depuis le Registre. Ce paramètre n’est significatif uniquement si `dwAccessType` est défini sur `INTERNET_OPEN_TYPE_PROXY`.  
  
 `dwFlags`  
 Indique les différentes options de mise en cache. La valeur par défaut est définie sur 0. Les valeurs possibles sont les suivantes :  
  
- `INTERNET_FLAG_DONT_CACHE`Ne mettent en cache les données, localement ou dans des serveurs de passerelle.  
  
- `INTERNET_FLAG_OFFLINE`Les opérations de téléchargement sont satisfaites via le cache persistant uniquement. Si l’élément n’existe pas dans le cache, un code d’erreur approprié est renvoyé. Cet indicateur peut être combiné avec l’opérateur de bits `OR` ( **|**) opérateur.  
  
### <a name="remarks"></a>Remarques  
 **CInternetSession** est la première fonction Internet appelée par une application. Il initialise les structures de données internes et le prépare pour les appels suivants à partir de l’application.  
  
 Si aucune connexion Internet ne peut être ouverte, `CInternetSession` lève une [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="close"></a>CInternetSession::Close  
 Appelez cette fonction membre lorsque votre application a terminé d’utiliser le `CInternetSession` objet.  
  
```  
virtual void Close();
```  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="enablestatuscallback"></a>CInternetSession::EnableStatusCallback  
 Appelez cette fonction membre pour permettre le rappel d’état.  
  
```  
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bEnable`  
 Spécifie si le rappel est activé ou désactivé. La valeur par défaut est **TRUE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Lors du traitement de rappel d’état, vous pouvez fournir l’état sur la progression de l’opération (par exemple, la résolution de nom, la connexion au serveur et ainsi de suite) dans la barre d’état de l’application. Affichage de l’état de l’opération convient surtout lors d’une opération à long terme.  
  
 Étant donné que les rappels se produisent pendant le traitement de la demande, l’application doit consacrer moins de temps possible dans le rappel afin d’éviter une dégradation du débit des données pour le réseau. Par exemple, la mise en place d’une boîte de dialogue dans un rappel peut être une opération longue que le serveur met fin à la demande.  
  
 Impossible de supprimer le rappel d’état tant que tous les rappels sont en attente.  
  
 Pour gérer toutes les opérations de façon asynchrone, vous devez créer votre propre thread ou utilisent les fonctions WinInet sans MFC.  
  
##  <a name="getcontext"></a>CInternetSession::GetContext  
 Appelez cette fonction membre pour obtenir la valeur de contexte pour une session d’application particulier.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le contexte défini par l’application identificateur.  
  
### <a name="remarks"></a>Remarques  
 [OnStatusCallback](#onstatuscallback) utilise l’ID de contexte retournée par **GetContext** pour signaler l’état d’une application particulière. Par exemple, lorsqu’un utilisateur lance une demande Internet qui implique le retour d’informations d’état, le rappel d’état utilise l’ID de contexte pour signaler l’état sur cette requête particulière. Si l’utilisateur Active deux que les deux impliquent retournant des informations d’état, les demandes Internet `OnStatusCallback` utilise les identificateurs de contexte pour renvoyer le statut concernant leurs demandes correspondants. Par conséquent, l’identificateur de contexte est utilisé pour toutes les opérations de rappel d’état, et il est associé à la session jusqu'à ce que la session est terminée.  
  
 Pour plus d’informations sur les opérations asynchrones, consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="getcookie"></a>CInternetSession::GetCookie  
 Cette fonction membre implémente le comportement de la fonction Win32 [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPTSTR pstrCookieData,  
    DWORD dwBufLen);

 
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    CString& strCookieData);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrUrl`  
 Pointeur vers une chaîne contenant l’URL.  
  
 `pstrCookieName`  
 Pointeur vers une chaîne contenant le nom du cookie pour obtenir de l’URL spécifiée.  
  
 `pstrCookieData`  
 Dans la première surcharge, un pointeur vers une chaîne contenant l’adresse de la mémoire tampon qui reçoit les données de cookie. Cette valeur peut être **NULL**. Dans la seconde surcharge, une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet pour recevoir les données de cookie.  
  
 `dwBufLen`  
 La variable en spécifiant la taille de la `pstrCookieData` mémoire tampon. Si la fonction réussit, la mémoire tampon reçoit la quantité de données copiée dans le `pstrCookieData` mémoire tampon. Si `pstrCookieData` est **NULL**, ce paramètre reçoit une valeur qui spécifie la taille de la mémoire tampon nécessaire pour copier toutes les données de cookie.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, ou **FALSE** dans le cas contraire. Si l’appel échoue, appelez la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) pour déterminer la cause de l’erreur. Les valeurs d’erreur suivantes s’appliquent :  
  
- **ERROR_NO_MORE_ITEMS** il y a aucun cookie pour l’URL spécifiée et tous ses parents.  
  
- **ERROR_INSUFFICIENT_BUFFER** la valeur transmise dans `dwBufLen` est insuffisant pour copier toutes les données de cookie. La valeur retournée dans `dwBufLen` est la taille de la mémoire tampon nécessaire pour obtenir toutes les données.  
  
### <a name="remarks"></a>Notes  
 Dans la seconde surcharge, MFC extrait les données de cookie dans fourni `CString` objet.  
  
##  <a name="getcookielength"></a>CInternetSession::GetCookieLength  
 Appelez cette fonction membre pour obtenir la longueur du cookie stocké dans la mémoire tampon.  
  
```  
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrUrl`  
 Un pointeur vers une chaîne contenant l’URL  
  
 `pstrCookieName`  
 Pointeur vers une chaîne contenant le nom du cookie.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` indiquant la longueur du cookie, stockée dans la mémoire tampon. Zéro si aucun cookie portant le nom indiqué par `pstrCookieName` existe.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur est utilisée par [GetCookie](#getcookie).  
  
##  <a name="getftpconnection"></a>CInternetSession::GetFtpConnection  
 Appelez cette fonction membre pour établir une connexion FTP et obtenir un pointeur vers un `CFtpConnection` objet.  
  
```  
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur FTP.  
  
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
  
 `bPassive`  
 Spécifie le mode passif ou actif pour cette session FTP. Si la valeur **TRUE**, il définit l’API Win32 `dwFlag` à **INTERNET_FLAG_PASSIVE**.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CFtpConnection](../../mfc/reference/cftpconnection-class.md) objet. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 `GetFtpConnection`se connecte à un serveur FTP et crée et retourne un pointeur vers un **CFTPConnection** objet. Il n’effectue pas une opération spécifique sur le serveur. Par exemple, si vous avez l’intention de lire ou écrire dans des fichiers, vous devez effectuer ces opérations séparément. Consultez les classes [CFtpConnection](../../mfc/reference/cftpconnection-class.md) et [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) pour plus d’informations sur la recherche de fichiers, ouverture de fichiers et lire ou écrire dans des fichiers. Consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md) pour les étapes de l’exécution des tâches courantes de connexion FTP.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="getgopherconnection"></a>CInternetSession::GetGopherConnection  
 Appelez cette fonction membre pour établir une connexion gopher et obtenir un pointeur vers un `CGopherConnection` objet.  
  
```  
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom de serveur gopher.  
  
 `pstrUserName`  
 Pointeur vers une chaîne contenant le nom d’utilisateur.  
  
 `pstrPassword`  
 Pointeur vers une chaîne contenant le mot de passe.  
  
 `nPort`  
 Numéro qui identifie le port TCP/IP à utiliser sur le serveur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md) objet. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 `GetGopherConnection`se connecte à un serveur gopher et crée et retourne un pointeur vers un `CGopherConnection` objet. Il n’effectue pas une opération spécifique sur le serveur. Par exemple, si vous avez l’intention de lire ou écrire des données, vous devez effectuer ces opérations séparément. Consultez les classes [objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), et [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) pour plus d’informations sur la recherche de fichiers, ouverture de fichiers et lire ou écrire dans des fichiers. Pour plus d’informations sur la navigation d’un site FTP, consultez la fonction membre [OpenURL](#openurl). Consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md) pour les étapes de l’exécution des tâches courantes de connexion gopher.  
  
##  <a name="gethttpconnection"></a>CInternetSession::GetHttpConnection  
 Appelez cette fonction membre pour établir une connexion HTTP et obtenir un pointeur vers un `CHttpConnection` objet.  
  
```  
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);

 
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur HTTP.  
  
 `nPort`  
 Numéro qui identifie le port TCP/IP à utiliser sur le serveur.  
  
 `pstrUserName`  
 Pointeur vers une chaîne contenant le nom d’utilisateur.  
  
 `pstrPassword`  
 Pointeur vers une chaîne contenant le mot de passe.  
  
 *dwFlags*  
 N’importe quelle combinaison de la **INTERNET_ FLAG_\* ** indicateurs. Consultez le tableau dans le **remarques** section de [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) pour obtenir une description de `dwFlags` valeurs.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) objet. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Notes  
 `GetHttpConnection`se connecte à un serveur HTTP et crée et retourne un pointeur vers un `CHttpConnection` objet. Il n’effectue pas une opération spécifique sur le serveur. Par exemple, si vous prévoyez d’interroger un en-tête HTTP, vous devez effectuer cette opération comme une étape distincte. Consultez les classes [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) et [CHttpFile](../../mfc/reference/chttpfile-class.md) pour plus d’informations sur les opérations que vous pouvez effectuer à l’aide d’une connexion à un serveur HTTP. Pour plus d’informations sur la navigation d’un site HTTP, consultez la fonction membre [OpenURL](#openurl). Consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md) pour les étapes de l’exécution des tâches courantes de connexion HTTP.  
  
##  <a name="onstatuscallback"></a>CInternetSession::OnStatusCallback  
 Cette fonction membre est appelée par l’infrastructure pour mettre à jour le statut lorsque le rappel d’état est activé et une opération est en attente.  
  
```  
virtual void OnStatusCallback(
    DWORD_PTR dwContext,  
    DWORD dwInternetStatus,  
    LPVOID lpvStatusInformation,  
    DWORD dwStatusInformationLength);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwContext`  
 La valeur de contexte fournie par l’application.  
  
 `dwInternetStatus`  
 Un code d’état qui indique la raison pour laquelle le rappel est effectué. Consultez la page **remarques** pour une table de valeurs possibles.  
  
 `lpvStatusInformation`  
 Pointeur vers une mémoire tampon contenant les informations relatives à ce rappel.  
  
 `dwStatusInformationLength`  
 Taille de `lpvStatusInformation`.  
  
### <a name="remarks"></a>Notes  
 Vous devez d’abord appeler [EnableStatusCallback](#enablestatuscallback) pour tirer parti de rappel d’état.  
  
 Le `dwInternetStatus` paramètre indique que l’opération en cours d’exécution et détermine la nature du contenu de `lpvStatusInformation` sera. `dwStatusInformationLength`Indique la longueur des données incluses dans `lpvStatusInformation`. Valeurs de l’état suivant pour `dwInternetStatus` sont définies comme suit :  
  
|Valeur|Signification|  
|-----------|-------------|  
|`INTERNET_STATUS_RESOLVING_NAME`|Recherche de l’adresse IP du nom contenu dans `lpvStatusInformation`.|  
|`INTERNET_STATUS_NAME_RESOLVED`|Réussi à trouver l’adresse IP du nom contenu dans `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Connexion à l’adresse de socket ( [SOCKADDR](../../mfc/reference/sockaddr-structure.md)) désigné par `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Correctement connecté à l’adresse de socket ( `SOCKADDR`) désigné par `lpvStatusInformation`.|  
|`INTERNET_STATUS_SENDING_REQUEST`|Envoi de la demande d’informations sur le serveur. Le `lpvStatusInformation` paramètre est **NULL**.|  
|**INTERNET_STATUS_ REQUEST_SENT**|Envoyé avec succès la demande d’informations sur le serveur. Le `lpvStatusInformation` paramètre est **NULL**.|  
|`INTERNET_STATUS_RECEIVING_RESPONSE`|En attente pour le serveur à répondre à une demande. Le `lpvStatusInformation` paramètre est **NULL**.|  
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Réception d’une réponse du serveur. Le `lpvStatusInformation` paramètre est **NULL**.|  
|`INTERNET_STATUS_CLOSING_CONNECTION`|Fermeture de la connexion au serveur. Le `lpvStatusInformation` paramètre est **NULL**.|  
|`INTERNET_STATUS_CONNECTION_CLOSED`|Correctement fermé la connexion au serveur. Le `lpvStatusInformation` paramètre est **NULL**.|  
|`INTERNET_STATUS_HANDLE_CREATED`|Utilisé par la fonction API Win32 [InternetConnect](http://msdn.microsoft.com/library/windows/desktop/aa384363) pour indiquer qu’il a créé le nouveau handle. Cela permet à la fonction application Win32 [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) à partir d’un autre thread, si la connexion est trop longue. Consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]pour plus d’informations sur ces fonctions.|  
|`INTERNET_STATUS_HANDLE_CLOSING`|Cette valeur de handle a été arrêtée correctement.|  
  
 Remplacez cette fonction membre pour demander une action avant l’exécution d’une routine de rappel d’état.  
  
> [!NOTE]
>  Rappels d’état besoin d’une protection de l’état du thread. Si vous utilisez MFC dans une bibliothèque partagée, ajoutez la ligne suivante au début du remplacement :  
  
 [!code-cpp[NVC_MFCHtmlHttp n °&8;](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]  
  
 Pour plus d’informations sur les opérations asynchrones, consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="openurl"></a>CInternetSession::OpenURL  
 Appelez ce membre de fonction pour envoyer la demande spécifiée pour le serveur HTTP et permettre au client de spécifier RFC822 supplémentaires, MIME ou en-têtes HTTP à envoyer avec la demande.  
  
```  
CStdioFile* OpenURL(
    LPCTSTR pstrURL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,  
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLength = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrURL*  
 Pointeur vers le nom de l’URL pour commencer la lecture. Seules les URL commençant par le fichier :, ftp :, gopher :, ou http : sont pris en charge. **ASSERTIONS** si *pszURL* est **NULL**.  
  
 `dwContext`  
 Une valeur définie par l’application passé avec le handle retourné dans le rappel.  
  
 `dwFlags`  
 Les indicateurs qui décrivent comment gérer cette connexion. Consultez la page **remarques** pour plus d’informations sur les indicateurs valides. Les indicateurs valides sont :  
  
- **INTERNET_FLAG_TRANSFER_ASCII** la valeur par défaut. Transférez le fichier en tant que texte ASCII.  
  
- **INTERNET_FLAG_TRANSFER_BINARY** transférer le fichier comme un fichier binaire.  
  
- `INTERNET_FLAG_RELOAD`Obtenir les données provenant du câble, même s’il est mis en cache localement.  
  
- `INTERNET_FLAG_DONT_CACHE`Ne mettent en cache les données, localement ou dans les passerelles.  
  
- `INTERNET_FLAG_SECURE`Cet indicateur est applicable aux demandes HTTP uniquement. Il demande des transactions sécurisées sur le câble avec Secure Sockets Layer ou pourcentage.  
  
- **INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT** si possible, de réutiliser les connexions existantes sur le serveur pour les nouvelles requêtes générées par **OpenUrl** au lieu de créer une nouvelle session pour chaque demande de connexion.  
  
- **INTERNET_FLAG_PASSIVE** utilisé pour un site FTP. Utilise FTP passif. Utilisé avec [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) de `OpenURL`.  
  
 `pstrHeaders`  
 Pointeur vers une chaîne contenant les en-têtes à envoyer au serveur HTTP.  
  
 *dwHeadersLength*  
 La longueur, en caractères, des en-têtes supplémentaires. S’il s’agit-1 L et `pstrHeaders` est non - **NULL**, puis `pstrHeaders` est supposé être égal à zéro s’est arrêté et la longueur est calculée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle de fichier pour seulement les services Internet de type de fichier, HTTP, FTP et GOPHER. Retourne **NULL** si l’analyse a échoué.  
  
 Le pointeur qui `OpenURL` retourne dépend *pszURL*du type de service. Le tableau ci-dessous illustre les pointeurs possible `OpenURL` peut retourner.  
  
|Type d’URL|Returns (Retours)|  
|--------------|-------------|  
|file://|**CStdioFile\***|  
|http://|**CHttpFile\***|  
|Gopher://|**CGopherFile\***|  
|FTP : / /|**CInternetFile\***|  
  
### <a name="remarks"></a>Notes  
 Le paramètre `dwFlags` doit inclure **INTERNET_FLAG_TRANSFER_ASCII** ou **INTERNET_FLAG_TRANSFER_BINARY**, mais pas les deux. Les indicateurs restants peuvent être combinées avec l’opérateur de bits `OR` (opérateur) ( **|**).  
  
 `OpenURL`, qui inclut la fonction Win32 **InternetOpenURL**, permet de télécharger uniquement, récupérer et lire les données à partir d’un serveur Internet. `OpenURL`ne permet à aucune manipulation de fichier sur un emplacement distant, afin qu’il ne nécessite aucune [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) objet.  
  
 Pour utiliser spécifique à la connexion (autrement dit, spécifiques au protocole) des fonctions, telles que l’écriture dans un fichier, vous devez ouvrir une session, puis ouvrez un type particulier de connexion, puis utiliser cette connexion pour ouvrir un fichier dans le mode souhaité. Consultez `CInternetConnection` pour plus d’informations sur les fonctions spécifiques à la connexion.  
  
##  <a name="operator_hinternet"></a>CInternetSession::operator HINTERNET  
 Utilisez cet opérateur pour obtenir le handle Windows de la session Internet.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="setcookie"></a>CInternetSession::SetCookie  
 Définit un cookie pour l’URL spécifiée.  
  
```  
static BOOL SetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPCTSTR pstrCookieData);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrUrl`  
 Pointeur vers une chaîne terminée par le caractère null qui spécifie l’URL pour lequel le cookie doit être défini.  
  
 `pstrCookieName`  
 Pointeur vers une chaîne contenant le nom du cookie.  
  
 `pstrCookieData`  
 Pointeur vers une chaîne contenant les données de chaîne réelle à associer à l’URL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, ou **FALSE** dans le cas contraire. Pour obtenir le code d’erreur spécifique, appelez **GetLastError.**  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setoption"></a>CInternetSession::SetOption  
 Appelez cette fonction membre pour définir des options pour la session Internet.  
  
```  
BOOL SetOption(
    DWORD dwOption,  
    LPVOID lpBuffer,  
    DWORD dwBufferLength,  
    DWORD dwFlags = 0);

 
BOOL SetOption(
    DWORD dwOption,  
    DWORD dwValue,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwOption`  
 L’option Internet à définir. Consultez la page [indicateurs d’Option](http://msdn.microsoft.com/library/windows/desktop/aa385328) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]pour obtenir la liste des options possibles.  
  
 `lpBuffer`  
 Une mémoire tampon qui contienne le paramètre d’option.  
  
 *dwBufferLength*  
 La longueur de `lpBuffer` ou la taille de `dwValue`.  
  
 `dwValue`  
 Un `DWORD` qui contient le paramètre d’option.  
  
 `dwFlags`  
 Indique les différentes options de mise en cache. La valeur par défaut est définie sur 0. Les valeurs possibles sont les suivantes :  
  
- `INTERNET_FLAG_DONT_CACHE`Ne mettent en cache les données, localement ou dans des serveurs de passerelle.  
  
- `INTERNET_FLAG_OFFLINE`Les opérations de téléchargement sont satisfaites via le cache persistant uniquement. Si l’élément n’existe pas dans le cache, un code d’erreur approprié est renvoyé. Cet indicateur peut être combiné avec l’opérateur de bits `OR` ( **|**) opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération a réussi, une valeur de **TRUE** est retourné. Si une erreur s’est produite, une valeur de **FALSE** est retourné. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)   
 [Classe d’objet CHttpConnection](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection (classe)](../../mfc/reference/cftpconnection-class.md)   
 [Classe d’objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md)

