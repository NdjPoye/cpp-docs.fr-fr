---
title: Classe de CAtlComModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
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
ms.openlocfilehash: 6b933b5388fccc2dc0e31d035aa7eb56de3b1866
ms.lasthandoff: 02/24/2017

---
# <a name="catlcommodule-class"></a>CAtlComModule (classe)
Cette classe implémente un module de serveur COM.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|Constructeur.|  
|[CAtlComModule :: ~ CAtlComModule](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|Appelez cette méthode pour mettre à jour le Registre système pour chaque objet du mappage d’objets.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|Appelez cette méthode pour inscrire une bibliothèque de types.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|Appelez cette méthode pour annuler l’inscription de chaque objet dans la table des objets.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|Appelez cette méthode pour annuler l’inscription d’une bibliothèque de types.|  
  
## <a name="remarks"></a>Remarques  
 `CAtlComModule`implémente un module de serveur COM, permettre à un client accéder aux composants du module.  
  
 Cette classe remplace obsolète [CComModule](../../atl/reference/ccommodule-class.md) classe utilisée dans les versions antérieures de l’ATL. Consultez la page [Classes du Module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="catlcommodule"></a>CAtlComModule::CAtlComModule  
 Constructeur.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise le module.  
  
##  <a name="dtor"></a>CAtlComModule :: ~ CAtlComModule  
 Destructeur.  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>Remarques  
 Libère toutes les fabriques de classes.  
  
##  <a name="registerserver"></a>CAtlComModule::RegisterServer  
 Appelez cette méthode pour mettre à jour le Registre système pour chaque objet du mappage d’objets.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRegTypeLib`  
 TRUE si la bibliothèque de types doit être enregistré. La valeur par défaut est FALSE.  
  
 `pCLSID`  
 Pointe vers le CLSID de l’objet à inscrire. Si NULL (valeur par défaut), tous les objets du mappage d’objets sera inscrit.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Appelle la fonction globale [AtlComModuleRegisterServer](http://msdn.microsoft.com/library/d11a0c91-0c56-4b1b-a5f5-1287970f798b).  
  
##  <a name="registertypelib"></a>CAtlComModule::RegisterTypeLib  
 Appelez cette méthode pour inscrire une bibliothèque de types.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszIndex`  
 Chaîne au format «\\\N », où N est l’index d’entiers de la ressource de bibliothèque de types.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Ajoute des informations sur une bibliothèque de types dans le Registre système. Si l’instance de module contient plusieurs bibliothèques de types, utilisez la première version de cette méthode pour spécifier le type de bibliothèque doit être utilisé.  
  
##  <a name="unregisterserver"></a>CAtlComModule::UnregisterServer  
 Appelez cette méthode pour annuler l’inscription de chaque objet dans la table des objets.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bRegTypeLib`  
 TRUE si la bibliothèque de types doit être annulée. La valeur par défaut est FALSE.  
  
 `pCLSID`  
 Pointe vers le CLSID de l’objet doit être annulée. Si la valeur NULL (valeur par défaut), tous les objets du mappage d’objets sera annulée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Appelle la fonction globale [AtlComModuleUnregisterServer](http://msdn.microsoft.com/library/c4ef3da4-def7-4aaf-b005-573a02e389d5).  
  
##  <a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib  
 Appelez cette méthode pour annuler l’inscription d’une bibliothèque de types.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszIndex`  
 Chaîne au format «\\\N », où N est l’index d’entiers de la ressource de bibliothèque de types.  
  
### <a name="remarks"></a>Notes  
 Supprime les informations sur une bibliothèque de types à partir du Registre système. Si l’instance de module contient plusieurs bibliothèques de types, utilisez la première version de cette méthode pour spécifier le type de bibliothèque doit être utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
## <a name="see-also"></a>Voir aussi  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

