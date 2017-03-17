---
title: "Classe d’objet CHttpConnection | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- protocols, HTTP
- connecting to servers, HTTP servers
- Internet protocols, HTTP
- HTTP connections
- Internet protocols
- CHttpConnection class
- HTTP servers, connecting to
- connecting to servers
- Internet connections, HTTP
- connections [C++], HTTP
- Internet server, HTTP
ms.assetid: a402b662-c445-4988-800d-c8278551babe
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1b02a79cebbd73a05478887115646f0544f0a92d
ms.lasthandoff: 02/24/2017

---
# <a name="chttpconnection-class"></a>Classe d’objet CHttpConnection
Gère votre connexion à un serveur HTTP.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|Crée un objet `CHttpConnection`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](#openrequest)|Ouvre une requête HTTP.|  
  
## <a name="remarks"></a>Remarques  
 HTTP est un des trois protocoles de serveur Internet implémentées par les classes WinInet MFC.  
  
 La classe `CHttpConnection` contient un constructeur et une fonction une membre [OpenRequest](#openrequest), qui gère les connexions à un serveur avec le protocole HTTP.  
  
 Pour communiquer avec un serveur HTTP, vous devez d’abord créer une instance de [CInternetSession](../../mfc/reference/cinternetsession-class.md), puis créez un [objet CHttpConnection](#_mfc_chttpconnection) objet. Vous ne créez jamais un `CHttpConnection` objet directement ; au lieu de cela, appelez [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), qui crée le `CHttpConnection` d’objet et retourne un pointeur vers elle.  
  
 Pour en savoir plus sur le `CHttpConnection` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md). Pour plus d’informations sur la connexion aux serveurs à l’aide de deux autres prises en charge des protocoles Internet, gopher et FTP, consultez les classes [objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md) et [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 Cette fonction membre est appelée pour construire un `CHttpConnection` objet.  
  
```  
CHttpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSession`  
 Un pointeur vers un [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet.  
  
 `hConnected`  
 Handle d’une connexion Internet.  
  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur.  
  
 `dwContext`  
 L’identificateur de contexte pour le `CInternetConnection` objet. Consultez la page **remarques** pour plus d’informations sur `dwContext`.  
  
 `nPort`  
 Numéro qui identifie le port Internet pour cette connexion.  
  
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
  
 `dwFlags`  
 N’importe quelle combinaison de la **INTERNET_ FLAG_\* ** indicateurs. Consultez le tableau dans le **remarques** section de [CHttpConnection::OpenRequest](#openrequest) pour obtenir une description de `dwFlags` valeurs.  
  
### <a name="remarks"></a>Notes  
 Vous ne créez jamais un `CHttpConnection` directement. Au lieu de cela, vous créez un objet en appelant [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).  
  
##  <a name="openrequest"></a>CHttpConnection::OpenRequest  
 Appelez cette fonction membre pour ouvrir une connexion HTTP.  
  
```  
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

 
CHttpFile* OpenRequest(
    int nVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrVerb`  
 Pointeur vers une chaîne contenant le verbe à utiliser dans la demande. Si `NULL`, « GET » est utilisé.  
  
 `pstrObjectName`  
 Pointeur vers une chaîne qui contient l’objet cible du verbe spécifié. C’est généralement un nom de fichier, un module exécutable ou d’un spécificateur de recherche.  
  
 `pstrReferer`  
 Un pointeur vers une chaîne qui spécifie l’adresse (URL) du document à partir duquel l’URL dans la demande ( `pstrObjectName`) a été obtenu. Si `NULL`, aucun en-tête HTTP n’est spécifié.  
  
 `dwContext`  
 L’identificateur de contexte pour le `OpenRequest` opération. Consultez la section Notes pour plus d’informations `dwContext`.  
  
 `ppstrAcceptTypes`  
 Un pointeur vers un tableau nul de `LPCTSTR` des pointeurs vers des chaînes indiquant les types de contenu accepté par le client. Si `ppstrAcceptTypes` est `NULL`, les serveurs interprètent que le client accepte uniquement des documents de type « texte / * » (autrement dit, les documents texte uniquement et pas images ou autres fichiers binaires). Le type de contenu est équivalent à la CONTENT_TYPE variable CGI, qui identifie le type de données pour les requêtes que vous ont lié des informations, tels que HTTP POST et PUT.  
  
 `pstrVersion`  
 Pointeur vers une chaîne définissant la version HTTP. Si `NULL`, « HTTP/1.0 » est utilisé.  
  
 `dwFlags`  
 N’importe quelle combinaison des indicateurs INTERNET_ FLAG_ *. Consultez la section Notes pour plus d’informations possible `dwFlags` valeurs.  
  
 `nVerb`  
 Un numéro associé au type de demande HTTP. Il peut s'agir d'une des valeurs suivantes :  
  
|Type de demande HTTP|Valeur `nVerb`|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le [CHttpFile](../../mfc/reference/chttpfile-class.md) objet demandé.  
  
### <a name="remarks"></a>Remarques  
 `dwFlags` peut avoir l'une des valeurs suivantes :  
  
|Indicateur d’Internet|Description|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|Force un téléchargement du fichier demandé, objet ou liste des répertoires à partir du serveur d’origine, pas à partir du cache.|  
|`INTERNET_FLAG_DONT_CACHE`|N’ajoute pas l’entité renvoyée dans le cache.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|Ajoute l’entité renvoyée dans le cache comme une entité persistante. Cela signifie que le nettoyage de cache standard, la vérification de cohérence ou le garbage collection ne peut pas supprimer cet élément à partir du cache.|  
|`INTERNET_FLAG_SECURE`|Utilise un sémantique de transaction. Cela se traduit par l’utilisation de SSL/PCT et n’est significative que dans les requêtes HTTP|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|Utilisé uniquement avec HTTP, spécifie que les redirections ne doivent pas automatiquement gérées dans [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Remplacer le `dwContext` par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est associé à cette opération spécifique de la `CHttpConnection` objet créé par son [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet. La valeur est retournée à [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’opération à laquelle elle est identifiée. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
 Exceptions peuvent être levées par cette fonction.  
  
## <a name="see-also"></a>Voir aussi  
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile (classe)](../../mfc/reference/chttpfile-class.md)

