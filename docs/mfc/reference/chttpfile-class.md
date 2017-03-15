---
title: Classe de CHttpFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpFile
dev_langs:
- C++
helpviewer_keywords:
- HTTP files
- HTTP requests, requesting and reading files
- CHttpFile class
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
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
ms.openlocfilehash: 0077c04f53514901dccaa3d162cd132578270225
ms.lasthandoff: 02/24/2017

---
# <a name="chttpfile-class"></a>CHttpFile (classe)
Fournit les fonctionnalités permettant de demander et de lire des fichiers sur un serveur HTTP.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|Crée un objet `CHttpFile`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Ajoute des en-têtes à la demande envoyée à un serveur HTTP.|  
|[CHttpFile::EndRequest](#endrequest)|Met fin à une demande envoyée à un serveur HTTP avec le [SendRequestEx](#sendrequestex) fonction membre.|  
|[CHttpFile::GetFileURL](#getfileurl)|Obtient l’URL pour le fichier spécifié.|  
|[CHttpFile::GetObject](#getobject)|Obtient l’objet cible de l’action dans une requête à un serveur HTTP.|  
|[CHttpFile::GetVerb](#getverb)|Obtient le verbe utilisé dans une requête à un serveur HTTP.|  
|[CHttpFile::QueryInfo](#queryinfo)|Retourne les en-têtes de réponse ou demande à partir du serveur HTTP.|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Récupère le code d’état associé à une requête HTTP et le place dans l’élément `dwStatusCode` paramètre.|  
|[CHttpFile::SendRequest](#sendrequest)|Envoie une demande à un serveur HTTP.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Envoie une demande à un serveur HTTP à l’aide du [écrire](../../mfc/reference/cinternetfile-class.md#write) ou [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) méthodes de `CInternetFile`.|  
  
## <a name="remarks"></a>Notes  
 Si votre session Internet lit des données à partir d’un serveur HTTP, vous devez créer une instance de `CHttpFile`.  
  
 Pour en savoir plus sur le `CHttpFile` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="a-nameaddrequestheadersa--chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders  
 Appelez cette fonction membre pour ajouter un ou plusieurs en-têtes de requête HTTP à la requête HTTP gérer.  
  
```  
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,  
    int dwHeadersLen = -1);

 
BOOL AddRequestHeaders(
    CString& str,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrHeaders`  
 Pointeur vers une chaîne contenant l’en-tête ou les en-têtes à ajouter à la demande. Chaque en-tête doit se terminer par une paire retour chariot/saut de ligne.  
  
 `dwFlags`  
 Modifie la sémantique des en-têtes de nouveau. Il peut s'agir d'une des valeurs suivantes :  
  
- `HTTP_ADDREQ_FLAG_COALESCE`Fusionne les en-têtes du même nom, à l’aide de l’indicateur pour ajouter le premier en-tête de l’en-tête suivant a été trouvé. Par exemple, « accepter : texte / * » suivie » accepter : audio /\*» entraîne la formation de l’en-tête « accepter : texte /\*, audio /\*». C’est à l’application appelante pour garantir un schéma cohérent en ce qui concerne les données reçues par des requêtes envoyées avec en-têtes fusionnés ou distincts.  
  
- `HTTP_ADDREQ_FLAG_REPLACE`Effectue une suppression et ajoutez pour remplacer l’en-tête actuel. Le nom d’en-tête permet de supprimer l’en-tête en cours, et la valeur complète sera utilisée pour ajouter le nouvel en-tête. Si la valeur d’en-tête est vide et que l’en-tête est trouvé, il est supprimé. Si ce n’est pas vide, la valeur d’en-tête est remplacée.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`Ajoute uniquement l’en-tête si elle n’existe pas déjà. S’il en existe, une erreur est renvoyée.  
  
- `HTTP_ADDREQ_FLAG_ADD`Utilisé avec remplacement. Ajoute l’en-tête si elle n’existe pas.  
  
 `dwHeadersLen`  
 La longueur, en caractères, de `pstrHeaders`. S’il s’agit-1 L, puis `pstrHeaders` est censée se terminer par zéro et la longueur est calculée.  
  
 `str`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant l’en-tête de demande ou l’ajout d’en-têtes.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Notes  
 `AddRequestHeaders`Ajoute des en-têtes supplémentaires, au format libre pour le handle de requête HTTP. Il est destiné à utiliser par les clients sophistiquées qui ont besoin d’un contrôle précis sur la demande exacte envoyée au serveur HTTP.  
  
> [!NOTE]
>  L’application peut passer plusieurs en-têtes dans `pstrHeaders` ou `str` pour un `AddRequestHeaders` appeler à l’aide de `HTTP_ADDREQ_FLAG_ADD` ou `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Si l’application essaie de supprimer ou remplacer un en-tête à l’aide de **HTTP_ADDREQ_FLAG_REMOVE** ou `HTTP_ADDREQ_FLAG_REPLACE`, un seul en-tête peut être fourni dans `lpszHeaders`.  
  
##  <a name="a-namechttpfilea--chttpfilechttpfile"></a><a name="chttpfile"></a>CHttpFile::CHttpFile  
 Cette fonction membre est appelée pour construire un `CHttpFile` objet.  
  
```  
CHttpFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrObject,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrVerb,  
    DWORD_PTR dwContext);

 
CHttpFile(
    HINTERNET hFile,  
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObject,  
    CHttpConnection* pConnection);
```  
  
### <a name="parameters"></a>Paramètres  
 `hFile`  
 Handle d’un fichier Internet.  
  
 `hSession`  
 Handle d’une session Internet.  
  
 *pstrObject*  
 Un pointeur vers une chaîne contenant le `CHttpFile` objet.  
  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur.  
  
 `pstrVerb`  
 Pointeur vers une chaîne qui contient la méthode à utiliser lors de l’envoi de la demande. Can be **POST**, **HEAD**, or `GET`.  
  
 dwContext  
 L’identificateur de contexte pour le `CHttpFile` objet. Consultez la page **remarques** pour plus d’informations sur ce paramètre.  
  
 `pConnection`  
 Un pointeur vers un [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Impossible de créer un `CHttpFile` directement l’objet, appelez plutôt [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) ou [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) à la place.  
  
 La valeur par défaut `dwContext` est envoyé par MFC pour le `CHttpFile` à partir de l’objet le [CInternetSession](../../mfc/reference/cinternetsession-class.md) de l’objet qui a créé le `CHttpFile` objet. Lorsque vous appelez `CInternetSession::OpenURL` ou `CHttpConnection` pour construire un `CHttpFile` de l’objet, vous pouvez remplacer la valeur par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est renvoyé au [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’objet avec lequel il est identifié. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
##  <a name="a-nameendrequesta--chttpfileendrequest"></a><a name="endrequest"></a>CHttpFile::EndRequest  
 Appelez cette fonction membre pour mettre fin à une demande envoyée à un serveur HTTP avec le [SendRequestEx](#sendrequestex) fonction membre.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Indicateurs décrivant l’opération. Pour obtenir la liste des indicateurs appropriés, consultez [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpBuffIn`  
 Pointeur vers un initialisé [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) qui décrit le tampon d’entrée utilisé pour l’opération.  
  
 `dwContext`  
 L’identificateur de contexte pour le `CHttpFile` opération. Pour plus d’informations sur ce paramètre, consultez la section Notes.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 La valeur par défaut `dwContext` est envoyé par MFC pour le `CHttpFile` à partir de l’objet le [CInternetSession](../../mfc/reference/cinternetsession-class.md) de l’objet qui a créé le `CHttpFile` objet. Lorsque vous appelez [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) ou [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) pour construire un `CHttpFile` de l’objet, vous pouvez remplacer la valeur par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est renvoyé au [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’objet avec lequel il est identifié. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
##  <a name="a-namegetfileurla--chttpfilegetfileurl"></a><a name="getfileurl"></a>CHttpFile::GetFileURL  
 Appelez cette fonction membre pour obtenir le nom du fichier sous forme d’URL HTTP.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui contient une URL qui référence la ressource associée à ce fichier.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction membre uniquement après un appel réussi à [SendRequest](#sendrequest) ou sur un `CHttpFile` objet créé avec succès par [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="a-namegetobjecta--chttpfilegetobject"></a><a name="getobject"></a>CHttpFile::GetObject  
 Appelez cette fonction membre pour obtenir le nom de l’objet associé à ce `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant le nom de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction membre uniquement après un appel réussi à [SendRequest](#sendrequest) ou sur un `CHttpFile` objet créé avec succès par [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="a-namegetverba--chttpfilegetverb"></a><a name="getverb"></a>CHttpFile::GetVerb  
 Appelez cette fonction membre pour récupérer le verbe HTTP (ou méthode) associé à ce `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant le nom du verbe HTTP (ou méthode).  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction membre uniquement après un appel réussi à [SendRequest](#sendrequest) ou sur un `CHttpFile` objet créé avec succès par [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="a-namequeryinfoa--chttpfilequeryinfo"></a><a name="queryinfo"></a>CHttpFile::QueryInfo  
 Appelez cette fonction membre pour retourner la réponse ou en-têtes de requête à partir d’une requête HTTP.  
  
```  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    LPVOID lpvBuffer,  
    LPDWORD lpdwBufferLength,  
    LPDWORD lpdwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    CString& str,  
    LPDWORD dwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    SYSTEMTIME* pSysTime,  
    LPDWORD dwIndex = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwInfoLevel`  
 Une combinaison de l’attribut à la requête et les indicateurs suivants qui spécifient le type d’informations demandés :  
  
- **HTTP_QUERY_CUSTOM** recherche le nom de l’en-tête et retourne cette valeur dans `lpvBuffer` en sortie. **HTTP_QUERY_CUSTOM** lève une assertion si l’en-tête n’est pas trouvée.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** en général, les en-têtes de réponse des requêtes de l’application, mais une application peut interroger également les en-têtes de requête à l’aide de cet indicateur.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** pour ces en-têtes dont la valeur est une chaîne de date/heure, tels que « Last-Modified-Time, » cet indicateur retourne la valeur d’en-tête comme Win32 standard [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure ne nécessitant pas de l’application pour analyser les données. Si vous utilisez cet indicateur, vous souhaiterez peut-être utiliser le `SYSTEMTIME` la substitution de la fonction.  
  
- **HTTP_QUERY_FLAG_NUMBER** pour ces en-têtes dont la valeur est un nombre, tel que le code d’état, cet indicateur retourne les données sous forme de nombre 32 bits.  
  
 Consultez le **notes** section pour obtenir la liste des valeurs possibles.  
  
 `lpvBuffer`  
 Pointeur vers la mémoire tampon qui reçoit les informations.  
  
 `lpdwBufferLength`  
 L’entrée, il pointe vers une valeur qui contient la longueur de la mémoire tampon, en nombre de caractères ou d’octets. Consultez le **notes** section pour plus d’informations sur ce paramètre.  
  
 `lpdwIndex`  
 Pointeur vers un index de base zéro d’en-tête. Peut être **NULL**. Utilisez cet indicateur pour énumérer plusieurs en-têtes avec le même nom. À l’entrée `lpdwIndex` indique l’index de l’en-tête spécifié à retourner. En sortie, `lpdwIndex` indique l’index de l’en-tête suivant. Si l’index suivant est introuvable, **ERROR_HTTP_HEADER_NOT_FOUND** est retourné.  
  
 `str`  
 Une référence à la [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui reçoit les informations renvoyées.  
  
 `dwIndex`  
 Valeur d’index. Consultez `lpdwIndex`.  
  
 *pSysTime*  
 Un pointeur vers un Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction membre uniquement après un appel réussi à [SendRequest](#sendrequest) ou sur un `CHttpFile` objet créé avec succès par [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Vous pouvez récupérer les types suivants de données à partir de `QueryInfo`:  
  
-   chaînes (par défaut)  
  
- `SYSTEMTIME`(pour « données : « « Expires : « en-têtes, etc.,)  
  
- `DWORD`(pour **STATUS_CODE**, **CONTENT_LENGTH**, etc..)  
  
 Lorsqu’une chaîne est écrite dans la mémoire tampon et la fonction membre réussit, `lpdwBufferLength` contient la longueur de la chaîne de caractères moins 1 de la fin de **NULL** caractère.  
  
 Les possibles `dwInfoLevel` valeurs incluent :  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="a-namequeryinfostatuscodea--chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a>CHttpFile::QueryInfoStatusCode  
 Appelez cette fonction membre pour obtenir le code d’état associé à une demande HTTP et la placer dans fourni `dwStatusCode` paramètre.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStatusCode`  
 Une référence à un code d’état. Codes d’état indiquent la réussite ou l’échec de l’événement demandé. Consultez la page **remarques** pour une sélection de descriptions de code d’état.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction membre uniquement après un appel réussi à [SendRequest](#sendrequest) ou sur un `CHttpFile` objet créé avec succès par [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Codes d’état HTTP sont répartis en groupes indiquant la réussite ou l’échec de la demande. Les tableaux suivants décrivent les groupes de codes d’état et les codes d’état HTTP courants.  
  
|Regrouper|Signification|  
|-----------|-------------|  
|200-299|Opération réussie|  
|300-399|Information|  
|400-499|Erreur de requête|  
|500-599|Erreur de serveur|  
  
 Codes d’état HTTP courants :  
  
|Code d'état|Signification|  
|-----------------|-------------|  
|200|L’URL est localisée, la transmission suit.|  
|400|Demande inintelligible|  
|404|Demande d’URL introuvable|  
|405|Serveur ne prend pas en charge la méthode demandée|  
|500|Erreur de serveur inconnue|  
|503|Capacité du serveur atteinte|  
  
##  <a name="a-namesendrequesta--chttpfilesendrequest"></a><a name="sendrequest"></a>CHttpFile::SendRequest  
 Appelez cette fonction membre pour envoyer une demande à un serveur HTTP.  
  
```  
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLen = 0,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);

 
BOOL SendRequest(
    CString& strHeaders,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrHeaders`  
 Pointeur vers une chaîne contenant le nom des en-têtes à envoyer.  
  
 `dwHeadersLen`  
 La longueur des en-têtes identifié par `pstrHeaders`.  
  
 `lpOptional`  
 Envoyer immédiatement après les en-têtes de demande des données facultatives. Ce paramètre est généralement utilisé pour **POST** et **PUT** operations. Cela peut être **NULL** si aucune donnée de facultatif à envoyer.  
  
 *dwOptionalLen*  
 Longueur de `lpOptional`.  
  
 `strHeaders`  
 Chaîne contenant le nom des en-têtes pour la requête envoyée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
##  <a name="a-namesendrequestexa--chttpfilesendrequestex"></a><a name="sendrequestex"></a>CHttpFile::SendRequestEx  
 Appelez cette fonction membre pour envoyer une demande à un serveur HTTP.  
  
```  
BOOL SendRequestEx(
    DWORD dwTotalLen,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);

 
BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,  
    LPINTERNET_BUFFERS lpBuffOut,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwTotalLen*  
 Nombre d’octets à envoyer dans la demande.  
  
 `dwFlags`  
 Indicateurs décrivant l’opération. Pour une liste des indicateurs appropriés, consultez [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 `dwContext`  
 L’identificateur de contexte pour le `CHttpFile` opération. Pour plus d’informations sur ce paramètre, consultez la section Notes.  
  
 `lpBuffIn`  
 Pointeur vers un initialisé [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) qui décrit le tampon d’entrée utilisé pour l’opération.  
  
 *lpBuffOut*  
 Pointeur vers un initialisé **INTERNET_BUFFERS** qui décrit la mémoire tampon de sortie utilisé pour l’opération.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération réussit. Si l’appel échoue, déterminer la cause du problème en examinant la levée [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet à votre application envoyer des données à l’aide de la [écrire](../../mfc/reference/cinternetfile-class.md#write) et [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) méthodes de `CInternetFile`. Vous devez connaître la longueur des données à envoyer avant d’appeler un remplacement de cette fonction. Le premier remplacement permet de spécifier la longueur des données que vous souhaitez envoyer. La deuxième substitution accepte des pointeurs vers **INTERNET_BUFFERS** structures, qui peuvent être utilisés pour décrire la mémoire tampon dans les moindres détails.  
  
 Une fois que le contenu est écrit dans le fichier, appelez [EndRequest](#endrequest) pour terminer l’opération.  
  
 La valeur par défaut `dwContext` est envoyé par MFC pour le `CHttpFile` à partir de l’objet le [CInternetSession](../../mfc/reference/cinternetsession-class.md) de l’objet qui a créé le `CHttpFile` objet. Lorsque vous appelez [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) ou [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md) pour construire un `CHttpFile` de l’objet, vous pouvez remplacer la valeur par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est renvoyé au [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’objet avec lequel il est identifié. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
### <a name="example"></a>Exemple  
 Ce fragment de code envoie le contenu d’une chaîne à une DLL nommée MFCISAPI. DLL sur le serveur LOCALHOST. Bien que cet exemple utilise un seul appel à `WriteString`, à l’aide de plusieurs appels à envoyer des données dans les blocs est acceptable.  
  
 [!code-cpp[NVC_MFCWinInet&#9;](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile (classe)](../../mfc/reference/cgopherfile-class.md)   
 [Classe d’objet CHttpConnection](../../mfc/reference/chttpconnection-class.md)

