---
title: Classe de CMonikerFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
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
ms.openlocfilehash: 4668672af1b33170ece1cb4d449ed5a20f6040e7
ms.lasthandoff: 02/24/2017

---
# <a name="cmonikerfile-class"></a>CMonikerFile (classe)
Représente un flux de données ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) nommé par une [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Construit un objet `CMonikerFile`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Détache et libère le flux et libère le moniker.|  
|[CMonikerFile::Detach](#detach)|Détache le `IMoniker` à partir de ce `CMonikerFile` objet.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Retourne le moniker actuel.|  
|[CMonikerFile::Open](#open)|Ouvre le fichier spécifié pour obtenir un flux de données.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Obtient le contexte de liaison ou crée un contexte de liaison initialisés par défaut.|  
  
## <a name="remarks"></a>Remarques  
 Un moniker contient des informations comme un chemin d’accès vers un fichier. Si vous avez un pointeur vers un objet de moniker `IMoniker` interface, vous pouvez accéder au fichier identifié sans avoir toute autre information spécifique sur l’emplacement du fichier réellement.  
  
 Dérivée de `COleStreamFile`, `CMonikerFile` prend un moniker ou une représentation de chaîne pouvant être transformé en un moniker et le lie au flux pour lequel le moniker est un nom. Vous pouvez ensuite lire et écrire dans ce flux de données. Le véritable objectif de `CMonikerFile` consiste à fournir un accès simple aux `IStream`s nommé par `IMoniker`s afin que vous n’avez pas à lier à un flux de données vous-même, encore avoir `CFile` fonctionnalité dans le flux.  
  
 `CMonikerFile`ne peut pas être utilisé pour lier à autre chose qu’un flux de données. Si vous souhaitez lier à un objet ou de stockage, vous devez utiliser le `IMoniker` directement de l’interface.  
  
 Pour plus d’informations sur les flux et les monikers, voir [COleStreamFile](../../mfc/reference/colestreamfile-class.md) dans les *référence MFC* et [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) et [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="close"></a>CMonikerFile::Close  
 Appelez cette fonction pour détacher et libérer le flux et libérer le moniker.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Notes  
 Peut être appelé sur un flux fermés ou déjà fermées.  
  
##  <a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 Construit un objet `CMonikerFile`.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 Appelez cette fonction pour créer un contexte de liaison initialisés par défaut.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Paramètres  
 `pError`  
 Pointeur vers une exception de fichier. En cas d’erreur, il est fixé à la cause.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le contexte de liaison [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) pour lier avec le cas de réussite ; sinon **NULL**. Si l’instance a été ouvert avec un `IBindHost` interface, le contexte de liaison est récupéré à partir de la `IBindHost`. S’il existe aucune `IBindHost` interface ou ne peut pas retourner un contexte de liaison, un contexte de liaison est créé. Pour obtenir une description de la [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) , consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Un contexte de liaison est un objet qui stocke des informations sur une opération de liaison de moniker particulier. Vous pouvez remplacer cette fonction afin de fournir un contexte de liaison personnalisée.  
  
##  <a name="detach"></a>CMonikerFile::Detach  
 Appelez cette fonction pour fermer le flux.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pError`  
 Pointeur vers une exception de fichier. En cas d’erreur, il est fixé à la cause.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="getmoniker"></a>CMonikerFile::GetMoniker  
 Appelez cette fonction pour récupérer un pointeur vers le moniker actuel.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’interface de moniker actuel ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Remarques  
 Étant donné que `CMonikerFile` n’est pas une interface, le pointeur retourné n’incrémente pas le décompte de références (via [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), et le moniker est libéré lorsque la `CMonikerFile` objet est libéré. Si vous souhaitez conserver le moniker ou libérer vous-même, vous devez `AddRef` il.  
  
##  <a name="open"></a>CMonikerFile::Open  
 Appelez cette fonction membre pour ouvrir un objet fichier ou moniker.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszURL`  
 URL ou nom du fichier à ouvrir.  
  
 `pError`  
 Pointeur vers une exception de fichier. En cas d’erreur, il est fixé à la cause.  
  
 `pMoniker`  
 Un pointeur vers l’interface moniker `IMoniker` à utiliser pour obtenir un flux de données.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le `lpszURL` paramètre ne peut pas être utilisé sur un ordinateur Macintosh. Uniquement les `pMoniker` forme de **Open** peut être utilisé sur un ordinateur Macintosh.  
  
 Vous pouvez utiliser une URL ou un nom de fichier pour le `lpszURL` paramètre. Exemple :  
  
 [!code-cpp[NVC_MFCWinInet n °&6;](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 – ou –  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [COleStreamFile (classe)](../../mfc/reference/colestreamfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

