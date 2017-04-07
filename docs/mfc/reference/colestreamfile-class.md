---
title: Classe de COleStreamFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- data streams [C++]
- streams [C++], OLE
- data streams [C++], OLE
- structured storage in OLE
- OLE structured storage [C++]
- OLE [C++], streams of data
- COleStreamFile class
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
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
ms.openlocfilehash: 0840d365f4179da0ad680256688eaf9484cb3cd8
ms.lasthandoff: 02/24/2017

---
# <a name="colestreamfile-class"></a>COleStreamFile (classe)
Représente un flux de données ( `IStream`) dans un fichier composé dans le cadre du stockage structuré OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Construit un objet `COleStreamFile`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Associe un flux de données à l’objet.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Crée un flux de données de la mémoire globale et l’associe à l’objet.|  
|[COleStreamFile::CreateStream](#createstream)|Crée un flux de données et l’associe à l’objet.|  
|[COleStreamFile::Detach](#detach)|Dissocie le flux à partir de l’objet.|  
|[COleStreamFile::GetStream](#getstream)|Retourne le flux actuel.|  
|[COleStreamFile::OpenStream](#openstream)|En toute sécurité ouvre un flux de données et l’associe à l’objet.|  
  
## <a name="remarks"></a>Remarques  
 Un `IStorage` objet doit exister avant que le flux peut être ouvert ou créé à moins qu’il s’agit d’un flux de mémoire.  
  
 `COleStreamFile`les objets sont manipulés exactement comme [CFile](../../mfc/reference/cfile-class.md) objets.  
  
 Pour plus d’informations sur la manipulation des flux et les stockages, consultez l’article [conteneurs : fichiers composés](../../mfc/containers-compound-files.md)...  
  
 Pour plus d’informations, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) et [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="attach"></a>COleStreamFile::Attach  
 Associe le flux OLE fourni avec les `COleStreamFile` objet.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpStream`  
 Pointe vers le flux OLE ( `IStream`) à associer à l’objet. Ne peut pas être **NULL**.  
  
### <a name="remarks"></a>Notes  
 L’objet ne doit pas déjà être associé à un flux OLE.  
  
 Pour plus d’informations, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 Crée un objet `COleStreamFile`.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpStream`  
 Pointeur vers le flux à associer à l’objet OLE.  
  
### <a name="remarks"></a>Notes  
 Si `lpStream` est **NULL**, l’objet n’est pas associé à un flux OLE, dans le cas contraire, l’objet est associé avec le flux OLE fourni.  
  
 Pour plus d’informations, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 En toute sécurité crée un flux de données manque de mémoire globale, partagée où une défaillance est une condition normale, attendue.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pError`  
 Pointe vers une [CFileException](../../mfc/reference/cfileexception-class.md) objet ou **NULL** qui indique l’état d’achèvement de l’opération de création. Spécifiez ce paramètre si vous souhaitez analyser les exceptions possibles générées en tentant de créer le flux de données.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le flux est créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 La mémoire est allouée par le sous-système OLE.  
  
 Pour plus d’informations, consultez [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="createstream"></a>COleStreamFile::CreateStream  
 En toute sécurité crée un flux de données dans l’objet de stockage fourni où une défaillance est une condition normale, attendue.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpStorage`  
 Pointe vers l’objet de stockage OLE qui contient le flux doit être créé. Ne peut pas être **NULL**.  
  
 `lpszStreamName`  
 Nom du flux doit être créé. Ne peut pas être **NULL**.  
  
 `nOpenFlags`  
 Mode d’accès à utiliser lors de l’ouverture du flux. Exclusif, lecture/écriture et créer des modes par défaut sont utilisées. Pour obtenir une liste complète des modes disponibles, consultez la page [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Pointe vers une [CFileException](../../mfc/reference/cfileexception-class.md) objet ou **NULL**. Spécifiez ce paramètre si vous souhaitez analyser les exceptions possibles générées en tentant de créer le flux de données.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le flux est créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Une exception de fichier sera levée si la fonction open échoue et `pError` n’est pas **NULL**.  
  
 Pour plus d’informations, consultez [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="detach"></a>COleStreamFile::Detach  
 Dissocie le flux à partir de l’objet sans avoir à fermer le flux de données.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le flux de données ( `IStream`) qui était associé à l’objet.  
  
### <a name="remarks"></a>Remarques  
 Le flux doit être fermé d’une autre façon avant la fin du programme.  
  
 Pour plus d’informations, consultez [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstream"></a>COleStreamFile::GetStream  
 Appelez cette fonction pour retourner un pointeur vers le flux actuel.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’interface actuelle du flux de données ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>COleStreamFile::OpenStream  
 Ouvre un flux existant.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpStorage`  
 Pointe vers l’objet de stockage OLE qui contient le flux doit être ouvert. Ne peut pas être **NULL**.  
  
 `lpszStreamName`  
 Nom du flux à ouvrir. Ne peut pas être **NULL**.  
  
 `nOpenFlags`  
 Mode d’accès à utiliser lors de l’ouverture du flux. Exclusif et en lecture/écriture modes sont utilisés par défaut. Pour obtenir la liste complète des modes disponibles, consultez la page [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 Pointe vers une [CFileException](../../mfc/reference/cfileexception-class.md) objet ou **NULL**. Spécifiez ce paramètre si vous souhaitez analyser les exceptions possibles générées en essayant d’ouvrir le flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le flux est ouvert avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Une exception de fichier sera levée si la fonction open échoue et `pError` n’est pas **NULL**.  
  
 Pour plus d’informations, consultez [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [CFile (classe)](../../mfc/reference/cfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




