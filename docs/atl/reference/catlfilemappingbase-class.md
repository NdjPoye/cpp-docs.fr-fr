---
title: Classe de CAtlFileMappingBase | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlFileMappingBase
- ATL::CAtlFileMappingBase
- CAtlFileMappingBase
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 439f123bc0addbbec2a26102d0197d0a1f14a8d5
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase (classe)
Cette classe représente un fichier mappé en mémoire.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Constructeur.|  
|[CAtlFileMappingBase :: ~ CAtlFileMappingBase](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Appelez cette méthode pour copier à partir d’un objet de mappage de fichier.|  
|[CAtlFileMappingBase::GetData](#getdata)|Appelez cette méthode pour obtenir les données à partir d’un objet de mappage de fichier.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Appelez cette méthode pour retourner le handle de fichier.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Appelez cette méthode pour obtenir la taille du mappage d’un objet de mappage de fichier.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Appelez cette méthode pour créer un objet de mappage de fichier.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Appelez cette méthode pour créer un objet de mappage de fichier qui permet un accès total à tous les processus.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Appelez cette méthode pour retourner un handle à l’objet de mappage de fichier.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Appelez cette méthode pour annuler le mappage d’un objet de mappage de fichier.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Définit l’objet de mappage de fichier en cours à un autre objet de mappage de fichier.|  
  
## <a name="remarks"></a>Remarques  
 Mappage de fichiers est l’association du contenu d’un fichier avec une partie de l’espace d’adressage virtuel d’un processus. Cette classe fournit des méthodes pour créer des objets de mappage de fichiers qui permettent d’accéder facilement et partager des données de programmes.  
  
 Pour plus d’informations, consultez [le mappage de fichiers](http://msdn.microsoft.com/library/windows/desktop/aa366556) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlfile.h  
  
##  <a name="a-namecatlfilemappingbasea--catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase  
 Constructeur.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `orig`  
 L’objet de mappage de fichier d’origine à copier pour créer le nouvel objet.  
  
### <a name="remarks"></a>Remarques  
 Crée un nouvel objet de mappage de fichier, en utilisant éventuellement un objet existant. Il est toujours nécessaire d’appeler [CAtlFileMappingBase::MapFile](#mapfile) pour ouvrir ou créer l’objet de mappage de fichier pour un fichier particulier.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Utilities&#71;](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="a-namedtora--catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFileMappingBase :: ~ CAtlFileMappingBase  
 Destructeur.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les ressources allouées par la classe et appelle le [CAtlFileMappingBase::Unmap](#unmap) (méthode).  
  
##  <a name="a-namecopyfroma--catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom  
 Appelez cette méthode pour copier à partir d’un objet de mappage de fichier.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `orig`  
 L’objet de mappage de fichier d’origine à copier à partir de.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` sur la réussite ou une erreur `HRESULT` en cas d’échec.  
  
##  <a name="a-namegetdataa--catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFileMappingBase::GetData  
 Appelez cette méthode pour obtenir les données à partir d’un objet de mappage de fichier.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers les données.  
  
##  <a name="a-namegethandlea--catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFileMappingBase::GetHandle  
 Appelez cette méthode pour retourner un handle à l’objet de mappage de fichier.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle vers l’objet de mappage de fichier.  
  
##  <a name="a-namegetmappingsizea--catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize  
 Appelez cette méthode pour obtenir la taille du mappage d’un objet de mappage de fichier.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la taille du mappage.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="a-namemapfilea--catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFileMappingBase::MapFile  
 Appelez cette méthode pour ouvrir ou créer un objet de mappage de fichier pour le fichier spécifié.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hFile`  
 Handle vers le fichier à partir duquel créer un objet de mappage. `hFile`doit être valide et ne peut pas avoir la valeur INVALID_HANDLE_VALUE.  
  
 `nMappingSize`  
 La taille du mappage. La valeur 0, la taille maximale de l’objet de mappage de fichier est égale à la taille actuelle du fichier identifié par *hFile.*  
  
 `nOffset`  
 Le décalage du fichier où la correspondance doit commencer. La valeur de décalage doit être un multiple de granularité d’allocation de mémoire du système.  
  
 `dwMappingProtection`  
 La protection souhaitée pour l’affichage du fichier lorsque le fichier est mappé. Consultez la page `flProtect` dans [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwViewDesiredAccess`  
 Spécifie le type d’accès à l’affichage des fichiers et, par conséquent, la protection des pages mappées par le fichier. Consultez la page `dwDesiredAccess` dans [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` sur la réussite ou une erreur `HRESULT` en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Après avoir créé un objet de mappage de fichier, la taille du fichier ne doit pas dépasser la taille de l’objet de mappage de fichier. Si c’est le cas, tous le contenu du fichier sera disponible pour le partage. Pour plus d’informations, consultez [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) et [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="a-namemapsharedmema--catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 Appelez cette méthode pour créer un objet de mappage de fichier qui permet un accès total à tous les processus.  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nMappingSize`  
 La taille du mappage. La valeur 0, la taille maximale de l’objet de mappage de fichier est égale à la taille actuelle de l’objet de mappage de fichier identifié par`szName.`  
  
 `szName`  
 Le nom de l’objet de mappage.  
  
 *pbAlreadyExisted*  
 Pointe vers une valeur Booléenne qui est déjà la valeur TRUE si l’objet de mappage existant.  
  
 `lpsa`  
 Le pointeur vers un **SECURITY_ATTRIBUTES** structure qui détermine si le handle retourné peut être hérité par les processus enfants. Consultez la page *lpAttributes* dans [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwMappingProtection`  
 La protection souhaitée pour l’affichage du fichier, lorsque le fichier est mappé. Consultez la page `flProtect` dans **CreateFileMapping** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwViewDesiredAccess`  
 Spécifie le type d’accès à l’affichage des fichiers et, par conséquent, la protection des pages mappées par le fichier. Consultez la page `dwDesiredAccess` dans [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` sur la réussite ou une erreur `HRESULT` en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 **MapShareMem** permet à un objet de mappage de fichier existant, créé par [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), pour être partagée entre plusieurs processus.  
  
##  <a name="a-nameopenmappinga--catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFileMappingBase::OpenMapping  
 Appelez cette méthode pour ouvrir un objet de mappage de fichier nommé pour le fichier spécifié.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `szName`  
 Le nom de l’objet de mappage. S’il existe un handle ouvert vers un objet de mappage de fichier portant ce nom et le descripteur de sécurité sur l’objet de mappage n’est pas en conflit avec le `dwViewDesiredAccess` paramètre, l’opération d’ouverture aboutisse.  
  
 `nMappingSize`  
 La taille du mappage. La valeur 0, la taille maximale de l’objet de mappage de fichier est égale à la taille actuelle de l’objet de mappage de fichier identifié par`szName.`  
  
 `nOffset`  
 Le décalage du fichier où la correspondance doit commencer. La valeur de décalage doit être un multiple de granularité d’allocation de mémoire du système.  
  
 `dwViewDesiredAccess`  
 Spécifie le type d’accès à l’affichage des fichiers et, par conséquent, la protection des pages mappées par le fichier. Consultez la page `dwDesiredAccess` dans [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` sur la réussite ou une erreur `HRESULT` en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Dans les versions debug, une erreur d’assertion se produira si les paramètres d’entrée ne sont pas valides.  
  
##  <a name="a-nameoperatoreqa--catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFileMappingBase::operator =  
 Définit l’objet de mappage de fichier en cours à un autre objet de mappage de fichier.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Paramètres  
 `orig`  
 L’objet de mappage de fichier en cours.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à l’objet actuel.  
  
##  <a name="a-nameunmapa--catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFileMappingBase::Unmap  
 Appelez cette méthode pour annuler le mappage d’un objet de mappage de fichier.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` sur la réussite ou une erreur `HRESULT` en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus de détails.  
  
## <a name="see-also"></a>Voir aussi  
 [CAtlFileMapping (classe)](../../atl/reference/catlfilemapping-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

