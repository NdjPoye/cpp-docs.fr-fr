---
title: Classe de CFileFind | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- files [C++], finding
- Internet files [C++], finding
- CFileFind class
- URLs [C++], searching for
- local files
- local files, searching for
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
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
ms.openlocfilehash: d7e6500dfc0ff24f35dd021a54080eb7ba7f1655
ms.lasthandoff: 02/24/2017

---
# <a name="cfilefind-class"></a>CFileFind (classe)
Effectue des recherches de fichiers local et est la classe de base pour [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) et [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), qui effectuent des recherches dans des fichiers Internet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Construit un objet `CFileFind`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Ferme la demande de recherche.|  
|[CFileFind::FindFile](#findfile)|Recherche dans un répertoire pour un nom de fichier spécifié.|  
|[CFileFind::FindNextFile](#findnextfile)|Continue la recherche d’un fichier à partir d’un appel précédent à [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Obtient l’heure de que création du fichier.|  
|[CFileFind::GetFileName](#getfilename)|Obtient le nom, y compris l’extension, du fichier trouvé|  
|[CFileFind::GetFilePath](#getfilepath)|Obtient le chemin d’accès complet du fichier trouvé.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Obtient le titre du fichier trouvé. Le titre n’inclut pas l’extension.|  
|[CFileFind::GetFileURL](#getfileurl)|Obtient l’URL, y compris le chemin d’accès, du fichier trouvé.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Obtient l’heure de dernier accès au fichier.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Obtient l’heure de la dernière modifié et le fichier enregistré.|  
|[CFileFind::GetLength](#getlength)|Obtient la longueur du fichier trouvé, en octets.|  
|[CFileFind::GetRoot](#getroot)|Obtient le répertoire racine du fichier trouvé.|  
|[CFileFind::IsArchived](#isarchived)|Détermine si le fichier est archivé.|  
|[CFileFind::IsCompressed](#iscompressed)|Détermine si le fichier est compressé.|  
|[CFileFind::IsDirectory](#isdirectory)|Détermine si le fichier est un répertoire.|  
|[CFileFind::IsDots](#isdots)|Détermine si le nom du fichier trouvé portant le nom «. « ou ».. », indiquant qu’il est en fait un répertoire.|  
|[CFileFind::IsHidden](#ishidden)|Détermine si le fichier trouvé est masqué.|  
|[CFileFind::IsNormal](#isnormal)|Détermine si le fichier trouvé est normal (en d’autres termes, n’a aucuns autres attributs).|  
|[CFileFind::IsReadOnly](#isreadonly)|Détermine si le fichier est en lecture seule.|  
|[CFileFind::IsSystem](#issystem)|Détermine si le fichier est un fichier système.|  
|[CFileFind::IsTemporary](#istemporary)|Détermine si le fichier trouvé est temporaire.|  
|[CFileFind::MatchesMask](#matchesmask)|Indique les attributs de fichier du fichier à rechercher.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Ferme le fichier spécifié par le handle de recherche actuel.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Pointeur vers un `CAtlTransactionManager` objet.|  
  
## <a name="remarks"></a>Notes  
 `CFileFind`inclut des fonctions membres qui lancer une recherche, recherchez un fichier et renvoient le titre, le nom ou le chemin d’accès du fichier. Pour les recherches sur Internet, la fonction membre [GetFileURL](#getfileurl) renvoie l’URL du fichier.  
  
 `CFileFind`est la classe de base pour les deux autres classes MFC conçue pour rechercher des types de serveur : `CGopherFileFind` fonctionne spécifiquement avec les serveurs gopher et `CFtpFileFind` fonctionne avec les serveurs FTP. Ensemble, ces trois classes fournissent un mécanisme transparent pour le client rechercher des fichiers, quel que soit le protocole de serveur, le type de fichier ou l’emplacement, sur un ordinateur local ou sur un serveur distant.  
  
 Le code suivant énumère tous les fichiers dans le répertoire actif, affiche le nom de chaque fichier :  
  
 [!code-cpp[NVC_MFCFiles&#31;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Pour simplifier l’exemple, ce code utilise la bibliothèque C++ Standard `cout` classe. Le `cout` ligne peut être remplacé par un appel à `CListBox::AddString`, par exemple, dans un programme avec une interface utilisateur graphique.  
  
 Pour plus d’informations sur l’utilisation de `CFileFind` et les autres classes WinInet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="cfilefind"></a>CFileFind::CFileFind  
 Cette fonction membre est appelée quand un `CFileFind` objet est construit.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTM`  
 Pointeur vers l'objet CAtlTransactionManager  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>CFileFind::Close  
 Appelez cette fonction membre pour mettre fin à la recherche, réinitialiser le contexte et libérer toutes les ressources.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé **fermer**, vous n’avez pas à créer un nouveau `CFileFind` instance avant d’appeler [FindFile](#findfile) pour commencer une nouvelle recherche.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>CFileFind::CloseContext  
 Ferme le fichier spécifié par le handle de recherche actuel.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Notes  
 Ferme le fichier spécifié par la valeur actuelle de la poignée de la recherche. Remplacez cette fonction pour modifier le comportement par défaut.  
  
 Vous devez appeler le [FindFile](#findfile) ou [FindNextFile](#findnextfile) fonctions au moins une fois pour récupérer un handle de recherche valide. Le **FindFile** et `FindNextFile` fonctions utilisent le handle de recherche pour rechercher des fichiers avec des noms qui correspondent à un nom donné.  
  
##  <a name="findfile"></a>CFileFind::FindFile  
 Appelez cette fonction membre pour ouvrir une recherche de fichier.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrName`  
 Pointeur vers une chaîne contenant le nom du fichier à rechercher. Si vous transmettez **NULL** de `pstrName`, **FindFile** est un caractère générique (*.\*) recherche.  
  
 *dwUnused*  
 Réservé pour rendre **FindFile** polymorphe avec les classes dérivées. Doit être 0.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Pour obtenir des informations d’erreur étendu appeler la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Notes  
 Après avoir appelé **FindFile** pour commencer la recherche de fichiers, appelez [FindNextFile](#findnextfile) pour extraire les fichiers suivants. Vous devez appeler `FindNextFile` au moins une fois avant d’appeler les fonctions membres d’attribut suivante :  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>CFileFind::FindNextFile  
 Appelez cette fonction membre pour poursuivre la recherche d’un fichier à partir d’un appel précédent à [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro s’il existe plusieurs fichiers ; zéro si le fichier est le dernier dans le répertoire ou si une erreur s’est produite. Pour obtenir des informations d’erreur étendu appeler la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Si le fichier est le dernier fichier dans le répertoire, ou si aucun des fichiers peuvent être trouvés, le `GetLastError` fonction renvoie ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler `FindNextFile` au moins une fois avant d’appeler les fonctions membres d’attribut suivante :  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile`encapsule la fonction Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>CFileFind::GetCreationTime  
 Appelez cette fonction membre pour obtenir l’heure de que création du fichier spécifié.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pTimeStamp`  
 Un pointeur vers un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure contenant l’heure de création du fichier.  
  
 `refTime`  
 Une référence à un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 en cas d’échec. `GetCreationTime`retourne 0 uniquement si [FindNextFile](#findnextfile) n’a jamais été appelée sur ce `CFileFind` objet.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetCreationTime`.  
  
> [!NOTE]
>  Pas tous les systèmes de fichiers utilisent la même sémantique pour implémenter l’horodatage retourné par cette fonction. Cette fonction peut retourner la même valeur retournée par d’autres fonctions de cachet de temps si le système de fichiers sous-jacent ou le serveur ne prend pas en charge en conservant l’attribut de durée. Consultez le [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure pour plus d’informations sur les formats d’heure. Sur certains systèmes d’exploitation, l’heure retournée est dans l’heure locale de zone à l’ordinateur ont été trouve le fichier. Consultez Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API pour plus d’informations.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>CFileFind::GetFileName  
 Appelez cette fonction membre pour obtenir le nom du fichier trouvé.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom du fichier récemment découvertes.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler GetFileName.  
  
 `GetFileName`est un des trois `CFileFind` fonctions membres qui retournent le nom de fichier. La liste suivante décrit les trois et comment elles varient :  
  
- `GetFileName`Retourne le nom de fichier, y compris l’extension. Par exemple, l’appel `GetFileName` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom de fichier `myfile.txt`.  
  
- [GetFilePath](#getfilepath) renvoie le chemin d’accès complet du fichier. Par exemple, l’appel `GetFilePath` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le chemin d’accès du fichier `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) retourne le nom de fichier, y compris l’extension de fichier. Par exemple, l’appel `GetFileTitle` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom du fichier `myfile`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles n°&32;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>CFileFind::GetFilePath  
 Appelez cette fonction membre pour obtenir le chemin d’accès complet du fichier spécifié.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le chemin d’accès du fichier spécifié.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetFilePath`.  
  
 `GetFilePath`est un des trois `CFileFind` fonctions membres qui retournent le nom de fichier. La liste suivante décrit les trois et comment elles varient :  
  
- [GetFileName](#getfilename) retourne le nom de fichier, y compris l’extension. Par exemple, l’appel `GetFileName` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom de fichier `myfile.txt`.  
  
- `GetFilePath`Retourne le chemin d’accès complet du fichier. Par exemple, l’appel `GetFilePath` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le chemin d’accès du fichier `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) retourne le nom de fichier, y compris l’extension de fichier. Par exemple, l’appel `GetFileTitle` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom du fichier `myfile`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>CFileFind::GetFileTitle  
 Appelez cette fonction membre pour obtenir le titre du fichier trouvé.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le titre du fichier.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetFileTitle`.  
  
 `GetFileTitle`est un des trois `CFileFind` fonctions membres qui retournent le nom de fichier. La liste suivante décrit les trois et comment elles varient :  
  
- [GetFileName](#getfilename) retourne le nom de fichier, y compris l’extension. Par exemple, l’appel `GetFileName` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom de fichier `myfile.txt`.  
  
- [GetFilePath](#getfilepath) renvoie le chemin d’accès complet du fichier. Par exemple, l’appel `GetFilePath` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le chemin d’accès du fichier `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle`Retourne le nom de fichier, y compris l’extension de fichier. Par exemple, l’appel `GetFileTitle` pour générer un message de l’utilisateur sur le fichier `c:\myhtml\myfile.txt` retourne le nom du fichier `myfile`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>CFileFind::GetFileURL  
 Appelez cette fonction membre pour récupérer l’URL spécifiée.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’URL complète.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetFileURL`.  
  
 `GetFileURL`est similaire à la fonction membre [GetFilePath](#getfilepath), à ceci près qu’elle renvoie l’URL sous la forme `file://path`. Par exemple, l’appel `GetFileURL` pour obtenir l’URL complète de `myfile.txt` renvoie l’URL `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime  
 Appelez cette fonction membre pour obtenir l’heure de dernier accès au fichier spécifié.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `refTime`  
 Une référence à un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet.  
  
 `pTimeStamp`  
 Un pointeur vers un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure contenant l’heure de dernier accès au fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 en cas d’échec. `GetLastAccessTime`retourne 0 uniquement si [FindNextFile](#findnextfile) n’a jamais été appelée sur ce `CFileFind` objet.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetLastAccessTime`.  
  
> [!NOTE]
>  Pas tous les systèmes de fichiers utilisent la même sémantique pour implémenter l’horodatage retourné par cette fonction. Cette fonction peut retourner la même valeur retournée par d’autres fonctions de cachet de temps si le système de fichiers sous-jacent ou le serveur ne prend pas en charge en conservant l’attribut de durée. Consultez le [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure pour plus d’informations sur les formats d’heure. Sur certains systèmes d’exploitation, l’heure retournée est dans l’heure locale de zone à l’ordinateur ont été trouve le fichier. Consultez Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API pour plus d’informations.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>CFileFind::GetLastWriteTime  
 Appelez cette fonction membre pour obtenir la dernière fois que le fichier a été modifié.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pTimeStamp`  
 Un pointeur vers un [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) structure contenant l’heure de la dernière écriture dans le fichier.  
  
 `refTime`  
 Une référence à un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; 0 en cas d’échec. `GetLastWriteTime`retourne 0 uniquement si [FindNextFile](#findnextfile) n’a jamais été appelée sur ce `CFileFind` objet.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetLastWriteTime`.  
  
> [!NOTE]
>  Pas tous les systèmes de fichiers utilisent la même sémantique pour implémenter l’horodatage retourné par cette fonction. Cette fonction peut retourner la même valeur retournée par d’autres fonctions de cachet de temps si le système de fichiers sous-jacent ou le serveur ne prend pas en charge en conservant l’attribut de durée. Consultez le [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure pour plus d’informations sur les formats d’heure. Sur certains systèmes d’exploitation, l’heure retournée est dans l’heure locale de zone à l’ordinateur ont été trouve le fichier. Consultez Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API pour plus d’informations.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>CFileFind::GetLength  
 Appelez cette fonction membre pour obtenir la longueur du fichier trouvé, en octets.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La longueur du fichier trouvé, en octets.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetLength`.  
  
 `GetLength`utilise la structure Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) pour obtenir et retourner la valeur de la taille du fichier en octets.  
  
> [!NOTE]
>  Depuis MFC 7.0, `GetLength` prend en charge les types d’entier 64 bits. Précédemment créé avec cette nouvelle version de la bibliothèque de code existant peut entraîner des avertissements de troncature.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#33;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>CFileFind::GetRoot  
 Appelez cette fonction membre pour obtenir la racine du fichier trouvé.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La racine de la recherche active.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `GetRoot`.  
  
 Cette fonction membre retourne le spécificateur de lecteur et le nom de chemin d’accès utilisé pour lancer une recherche. Par exemple, l’appel [FindFile](#findfile) avec `*.dat` entraîne `GetRoot` retournant une chaîne vide. En passant un chemin d’accès, tel que `c:\windows\system\*.dll`, **FindFile** résultats `GetRoot` retourner `c:\windows\system\`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>CFileFind::IsArchived  
 Appelez cette fonction membre pour déterminer si le fichier est archivé.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Applications de marquer un fichier d’archive, qui doit être sauvegardé ou supprimé, à FILE_ATTRIBUTE_ARCHIVE, un attribut de fichier identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsArchived`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>CFileFind::IsCompressed  
 Appelez cette fonction membre pour déterminer si le fichier est compressé.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un fichier compressé est marqué avec FILE_ATTRIBUTE_COMPRESSED, un attribut de fichier est identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Pour un fichier, cet attribut indique que toutes les données dans le fichier est compressé. Pour un répertoire, cet attribut indique que la compression est la valeur par défaut pour les fichiers nouvellement créées et les sous-répertoires.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsCompressed`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>CFileFind::IsDirectory  
 Appelez cette fonction membre pour déterminer si le fichier est un répertoire.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un fichier est un répertoire est marqué avec FILE_ATTRIBUTE_DIRECTORY un attribut de fichier est identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsDirectory`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
 Ce petit programme parcourt chaque répertoire sur le lecteur C:\ et imprime le nom du répertoire.  
  
 [!code-cpp[NVC_MFCFiles&#34;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>CFileFind::IsDots  
 Appelez cette fonction membre pour tester les marqueurs d’Active directory et parent actuels lors de l’itération dans les fichiers.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le fichier porte le nom «. « ou ».. », ce qui signifie que le fichier est un répertoire. Sinon 0.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsDots`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>CFileFind::IsHidden  
 Appelez cette fonction membre pour déterminer si le fichier trouvé est masqué.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Les fichiers cachés, qui sont marqués avec FILE_ATTRIBUTE_HIDDEN, un attribut de fichier identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Un fichier masqué n’est pas inclus dans une liste de répertoires ordinaires.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsHidden`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>CFileFind::IsNormal  
 Appelez cette fonction membre pour déterminer si le fichier est un fichier normal.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Les fichiers marqués avec FILE_ATTRIBUTE_NORMAL, un attribut de fichier identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Un fichier normal n’a aucuns autres attributs à définir. Tous les autres attributs de fichier remplacent cet attribut.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsNormal`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>CFileFind::IsReadOnly  
 Appelez cette fonction membre pour déterminer si le fichier est en lecture seule.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un fichier en lecture seule est marqué avec ATTRIBUT_FICHIER_LECTURESEULE, identifié par un attribut de fichier dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Applications peuvent lire ce type de fichier, mais ils ne peuvent pas écrire dedans ou le supprimer.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsReadOnly`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>CFileFind::IsSystem  
 Appelez cette fonction membre pour déterminer si le fichier est un fichier système.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Un fichier système est marqué avec FILE_ATTRIBUTE_SYSTEM, identifié par un attribut de fichier dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Fait partie d’un fichier système, ou est utilisé exclusivement par le système d’exploitation.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsSystem`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>CFileFind::IsTemporary  
 Appelez cette fonction membre pour déterminer si le fichier est un fichier temporaire.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Un fichier temporaire est marqué avec FILE_ATTRIBUTE_TEMPORARY, un attribut de fichier est identifié dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Un fichier temporaire est utilisé pour le stockage temporaire. Les applications doivent écrire dans le fichier uniquement en cas de nécessité absolue. La plupart des données du fichier reste en mémoire sans vidée au support, car le fichier sera supprimé prochainement.  
  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `IsTemporary`.  
  
 Consultez la fonction membre [MatchesMask](#matchesmask) pour une liste complète des attributs de fichier.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>CFileFind::m_pTM  
 Pointeur vers un `CAtlTransactionManager` objet.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="matchesmask"></a>CFileFind::MatchesMask  
 Appelez cette fonction membre pour tester les attributs de fichier sur le fichier trouvé.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwMask`  
 Spécifie un ou plusieurs attributs de fichier identifiés dans le [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure, pour le fichier trouvé. Pour rechercher plusieurs attributs, utilisez l’opérateur de bits OR (opérateur) (|). N’importe quelle combinaison des attributs suivants est acceptable :  
  
-   FILE_ATTRIBUTE_ARCHIVE le fichier est un fichier d’archive. Les applications utilisent cet attribut pour marquer les fichiers pour la sauvegarde ou de suppression.  
  
-   FILE_ATTRIBUTE_COMPRESSED le fichier ou le répertoire est compressé. Pour un fichier, cela signifie que toutes les données dans le fichier est compressé. Pour un répertoire, cela signifie que la compression est la valeur par défaut pour les fichiers nouvellement créées et les sous-répertoires.  
  
-   FILE_ATTRIBUTE_DIRECTORY le fichier est un répertoire.  
  
-   FILE_ATTRIBUTE_NORMAL le fichier n’a aucuns autres attributs à définir. Cet attribut est valide uniquement si utilisé seul. Tous les autres attributs de fichier remplacent cet attribut.  
  
-   FILE_ATTRIBUTE_HIDDEN le fichier est masqué. Il ne pas être inclus dans une liste de répertoires ordinaires.  
  
-   ATTRIBUT_FICHIER_LECTURESEULE le fichier est en lecture seule. Les applications peuvent lire le fichier mais ne peut pas y accéder en écriture ou supprimez-la.  
  
-   FILE_ATTRIBUTE_SYSTEM le fichier fait partie d’ou est utilisé exclusivement par le système d’exploitation.  
  
-   FILE_ATTRIBUTE_TEMPORARY le fichier est utilisé pour le stockage temporaire. Les applications doivent écrire dans le fichier uniquement en cas de nécessité absolue. La plupart des données du fichier reste en mémoire sans vidée au support, car le fichier sera supprimé prochainement.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Pour obtenir des informations d’erreur étendu appeler la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler [FindNextFile](#findnextfile) au moins une fois avant d’appeler `MatchesMask`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#35;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind (classe)](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind (classe)](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile (classe)](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile (classe)](../../mfc/reference/chttpfile-class.md)
