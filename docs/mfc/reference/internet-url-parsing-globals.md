---
title: "Objet Globals d’analyse des URL Internet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 3aec259acae2f5e9c9b65ac4e5c898ca57ff3d52
ms.lasthandoff: 02/24/2017

---
# <a name="internet-url-parsing-globals"></a>Objet Globals d'analyse des URL Internet
Lorsqu’un client envoie une requête au serveur Internet, vous pouvez utiliser une des URL de l’objet globals d’analyse pour extraire des informations sur le client.  
  
### <a name="internet-url-parsing-globals"></a>Objet Globals d'analyse des URL Internet  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Analyse une chaîne URL et retourne le type de service et de ses composants.|  
|[AfxParseURLEx](#afxparseurlex)|Analyse une chaîne URL et retourne le type de service et ses composants, ainsi en fournissant le nom d’utilisateur et le mot de passe.|  
  
##  <a name="a-nameafxparseurla--afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL  
 Ce global est utilisé dans [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrURL*  
 Pointeur vers une chaîne contenant l’URL à analyser.  
  
 `dwServiceType`  
 Indique le type de service Internet. Les valeurs possibles sont les suivantes :  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Le premier segment de l’URL qui suit le type de service.  
  
 `strObject`  
 Un objet qui représente l’URL (peut être vide).  
  
 `nPort`  
 Déterminé à partir de l’objet ou serveur portions de l’URL, si elles existent.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’URL a été analysée avec succès ; Sinon, 0 si elle est vide ou ne contient pas un type de service Internet connu.  
  
### <a name="remarks"></a>Remarques  
 Il analyse une chaîne URL et retourne le type de service et de ses composants.  
  
 Par exemple, `AfxParseURL` analyse les URL de la forme **service://server/dir/dir/object.ext:port** et retourne ses composants, comme suits :  
  
 `strServer`== « serveur »  
  
 `strObject`== « / dir/dir/object/object.ext »  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Pour appeler cette fonction, votre projet doit inclure AFXINET. H.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxinet.h  
  
##  <a name="a-nameafxparseurlexa--afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx  
 Cette fonction globale est la version étendue du [AfxParseURL](#afxparseurl) et est utilisée dans [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrURL*  
 Pointeur vers une chaîne contenant l’URL à analyser.  
  
 `dwServiceType`  
 Indique le type de service Internet. Les valeurs possibles sont les suivantes :  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Le premier segment de l’URL qui suit le type de service.  
  
 `strObject`  
 Un objet qui représente l’URL (peut être vide).  
  
 `nPort`  
 Déterminé à partir de l’objet ou serveur portions de l’URL, si elles existent.  
  
 *strUsername*  
 Une référence à un `CString` objet contenant le nom de l’utilisateur.  
  
 `strPassword`  
 Une référence à un `CString` objet contenant le mot de passe de l’utilisateur.  
  
 `dwFlags`  
 Les indicateurs de contrôle de l’analyse de l’URL. Peut être une combinaison des valeurs suivantes :  
  
|Valeur|Signification|  
|-----------|-------------|  
|**ICU_DECODE**|Convertir les séquences d’échappement % XX en caractères.|  
|**ICU_NO_ENCODE**|Ne pas convertir les caractères non sécurisés en séquence d’échappement.|  
|**ICU_NO_META**|Ne supprimez pas les séquences de métadonnées (par exemple, « \ ». et « \ »...) à partir de l’URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Encoder uniquement des espaces.|  
|**ICU_BROWSER_MODE**|Ne pas encoder ou décoder les caractères après « # » ou « » et ne supprimez pas l’espace blanc de fin après ». Si cette valeur n’est pas spécifiée, l’URL entière est encodé et espace blanc de fin est supprimé.|  
  
 Si vous utilisez la valeur par défaut MFC, c'est-à-dire aucun indicateur, la fonction convertit tous les caractères non sécurisés et les séquences de métadonnées (tel que \\., \.., et \\...) pour échapper les séquences.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’URL a été analysée avec succès ; Sinon, 0 si elle est vide ou ne contient pas un type de service Internet connu.  
  
### <a name="remarks"></a>Remarques  
 Il analyse une chaîne URL et retourne le type de service et ses composants, ainsi en fournissant le nom et le mot de passe de l’utilisateur. Les indicateurs indiquent comment unsafe caractères sont gérées.  
  
> [!NOTE]
>  Pour appeler cette fonction, votre projet doit inclure AFXINET. H.  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxinet.h  
    
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

