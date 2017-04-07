---
title: Classe de CInternetConnection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- asynchronous connections
- CInternetConnection class
- Internet connections
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
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
ms.openlocfilehash: 7f99562e0c6103fc3f46a7fe28f9d2f2efff0a01
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetconnection-class"></a>CInternetConnection (classe)
Gère votre connexion à un serveur Internet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Construit un objet `CInternetConnection`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Obtient l’ID de contexte pour cet objet de connexion.|  
|[CInternetConnection::GetServerName](#getservername)|Obtient le nom du serveur associé à la connexion.|  
|[CInternetConnection::GetSession](#getsession)|Obtient un pointeur vers le [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet associé à la connexion.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Handle d’une session Internet.|  
  
## <a name="remarks"></a>Remarques  
 C’est la classe de base pour les classes MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [objet CHttpConnection](../../mfc/reference/chttpconnection-class.md), et [objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Chacune de ces classes fournit des fonctionnalités supplémentaires pour la communication avec le serveur FTP, HTTP et gopher respectif.  
  
 Pour communiquer directement avec un serveur Internet, vous devez avoir un [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet et un `CInternetConnection` objet.  
  
 Pour plus d’informations sur la façon dont fonctionnent les classes de WinInet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 Cette fonction membre est appelée quand un `CInternetConnection` objet est créé.  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSession`  
 Un pointeur vers un [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet.  
  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur.  
  
 `nPort`  
 Numéro qui identifie le port Internet pour cette connexion.  
  
 `dwContext`  
 L’identificateur de contexte pour le `CInternetConnection` objet. Consultez la page **remarques** pour plus d’informations sur `dwContext`.  
  
### <a name="remarks"></a>Remarques  
 Ne jamais appeler `CInternetConnection` ; au lieu de cela, appelez le [CInternetSession](../../mfc/reference/cinternetsession-class.md) fonction membre pour le type de connexion que vous souhaitez établir :  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 La valeur par défaut `dwContext` est envoyé par MFC pour le `CInternetConnection`-objet dérivé le [CInternetSession](../../mfc/reference/cinternetsession-class.md) de l’objet qui a créé le **InternetConnection**-objet dérivé. La valeur par défaut est défini sur 1. Toutefois, vous pouvez affecter explicitement un identificateur de contexte spécifique dans le [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) constructeur pour la connexion. L’objet et tout travail qu’elle effectue est associées à cet ID de contexte. L’identificateur de contexte est renvoyé au [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’objet avec lequel il est identifié. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
##  <a name="getcontext"></a>CInternetConnection::GetContext  
 Appelez cette fonction membre pour obtenir l’ID de contexte pour cette session.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’ID de contexte d’application affectée.  
  
### <a name="remarks"></a>Remarques  
 L’ID de contexte est spécifié à l’origine dans [CInternetSession](../../mfc/reference/cinternetsession-class.md) et se propage à `CInternetConnection`- et [CInternetFile](../../mfc/reference/cinternetfile-class.md)-les classes dérivées, sauf indication différemment dans l’appel à une fonction qui ouvre la connexion. L’ID de contexte est associé à une opération de l’objet donné et identifie les informations d’état de l’opération retournées par [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Pour plus d’informations sur la **GetContext** fonctionne avec d’autres classes WinInet pour donner les informations d’état utilisateur, consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
##  <a name="getservername"></a>CInternetConnection::GetServerName  
 Appelez cette fonction membre pour obtenir le nom du serveur associé à cette connexion Internet.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom du serveur que cet objet de connexion fonctionne.  
  
##  <a name="getsession"></a>CInternetConnection::GetSession  
 Appelez cette fonction membre pour obtenir un pointeur vers le `CInternetSession` objet associé à cette connexion.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CInternetSession](../../mfc/reference/cinternetsession-class.md) objet associé à cet objet de connexion Internet.  
  
##  <a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 Utilisez cet opérateur pour obtenir le handle de niveau API pour la session Internet.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




