---
title: CFtpFileFind (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpFileFind
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind class
- file searches [C++]
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
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
ms.openlocfilehash: 6e84282cc2f22e813ea44318d497c7e32e3280d8
ms.lasthandoff: 02/24/2017

---
# <a name="cftpfilefind-class"></a>CFtpFileFind (classe)
Contribue à la recherche des fichiers Internet sur les serveurs FTP.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Construit un objet `CFtpFileFind`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](#findfile)|Recherche un fichier sur un serveur FTP.|  
|[CFtpFileFind::FindNextFile](#findnextfile)|Continue la recherche d’un fichier à partir d’un appel précédent à [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Obtient l’URL, y compris le chemin d’accès du fichier trouvé.|  
  
## <a name="remarks"></a>Notes  
 `CFtpFileFind`inclut des fonctions membres qui lancer une recherche, recherchez un fichier et retournent l’URL ou autres informations descriptives sur le fichier.  
  
 Classes de MFC conçus pour rechercher un fichier local et Internet incluent [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) et [CFileFind](../../mfc/reference/cfilefind-class.md). Avec `CFtpFileFind`, ces classes fournissent un mécanisme transparent pour le client trouver des fichiers spécifiques, quel que soit le serveur de type de fichier ou de protocole (un ordinateur local ou un serveur distant). Notez qu’il n’existe aucune classe MFC pour la recherche sur les serveurs HTTP car HTTP ne prend pas en charge la manipulation directe de fichiers requise pour les recherches.  
  
 Pour plus d’informations sur l’utilisation de `CFtpFileFind` et les autres classes WinInet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Exemple  
 Le code suivant montre comment énumérer tous les fichiers dans le répertoire actif du serveur FTP.  
  
 [!code-cpp[NVC_MFCWinInet n °&8;](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="a-namecftpfilefinda--cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 Cette fonction membre est appelée pour construire un `CFtpFileFind` objet.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Paramètres  
 `pConnection`  
 Un pointeur vers un `CFtpConnection` objet. Vous pouvez obtenir une connexion FTP en appelant [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 `dwContext`  
 L’identificateur de contexte pour le `CFtpFileFind` objet. Consultez la page **remarques** pour plus d’informations sur ce paramètre.  
  
### <a name="remarks"></a>Remarques  
 La valeur par défaut `dwContext` est envoyé par MFC pour le `CFtpFileFind` à partir de l’objet le [CInternetSession](../../mfc/reference/cinternetsession-class.md) de l’objet qui a créé le `CFtpFileFind` objet. Vous pouvez remplacer la valeur par défaut pour définir l’identificateur de contexte pour une valeur de votre choix. L’identificateur de contexte est renvoyé au [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) pour fournir l’état de l’objet avec lequel il est identifié. Consultez l’article [Internet premières étapes : WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de la vue d’ensemble de la classe précédemment dans cette rubrique.  
  
##  <a name="a-namefindfilea--cftpfilefindfindfile"></a><a name="findfile"></a>CFtpFileFind::FindFile  
 Appelez cette fonction membre pour rechercher un fichier FTP.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrName`  
 Pointeur vers une chaîne contenant le nom du fichier à rechercher. Si **NULL**, l’appel effectue une recherche générique (*).  
  
 `dwFlags`  
 Les indicateurs qui décrivent comment gérer cette session. Ces indicateurs peuvent être combinés avec l’opérateur OR (|) et sont les suivantes :  
  
-   INTERNET_FLAG_RELOAD obtenir les données provenant du câble, même s’il est mis en cache localement. Il s’agit de l’indicateur par défaut.  
  
-   Faire INTERNET_FLAG_DONT_CACHE met pas en cache les données, localement ou dans les passerelles.  
  
-   INTERNET_FLAG_RAW_DATA remplacer la valeur par défaut pour retourner les données brutes ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structures pour FTP).  
  
-   INTERNET_FLAG_SECURE sécurise les transactions sur le réseau avec le protocole SSL (Secure Sockets Layer) ou PCT. Cet indicateur est applicable aux demandes HTTP uniquement.  
  
-   INTERNET_FLAG_EXISTING_CONNECT si possible, réutiliser les connexions existantes sur le serveur pour les nouveaux **FindFile** demandes au lieu de créer une nouvelle session pour chaque demande.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Pour obtenir des informations d’erreur étendu appeler la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé **FindFile** pour récupérer le premier fichier FTP, vous pouvez appeler [FindNextFile](#findnextfile) pour récupérer les fichiers FTP.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple précédent dans cette rubrique.  
  
##  <a name="a-namefindnextfilea--cftpfilefindfindnextfile"></a><a name="findnextfile"></a>CFtpFileFind::FindNextFile  
 Appelez cette fonction membre pour continuer une recherche de fichier lancée par un appel à la [FindFile](#findfile) fonction membre.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro s’il existe plusieurs fichiers ; zéro si le fichier est le dernier dans le répertoire ou si une erreur s’est produite. Pour obtenir des informations d’erreur étendu appeler la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Si le fichier est le dernier fichier dans le répertoire, ou si aucun des fichiers peuvent être trouvés, le `GetLastError` fonction renvoie ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler cette fonction au moins une fois avant d’appeler toute fonction de l’attribut (voir [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`encapsule la fonction Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple plus haut dans cette rubrique.  
  
##  <a name="a-namegetfileurla--cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 Appelez cette fonction membre pour obtenir l’URL du fichier spécifié.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le fichier et le chemin d’accès de l’URL Universal Resource Locator ().  
  
### <a name="remarks"></a>Remarques  
 `GetFileURL`est similaire à la fonction membre [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), à ceci près qu’elle renvoie l’URL sous la forme `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>Voir aussi  
 [CFileFind (classe)](../../mfc/reference/cfilefind-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind (classe)](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile (classe)](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile (classe)](../../mfc/reference/chttpfile-class.md)

