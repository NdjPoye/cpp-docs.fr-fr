---
title: Classe de CAtlBaseModule | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07f1252fe993ff2f2e646528996c1a53d25c5a63
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="catlbasemodule-class"></a>Classe de CAtlBaseModule
Cette classe est instanciée dans chaque projet ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Ajoute une instance de la ressource à la liste des handles stockées.|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Retourne un handle vers une instance de la ressource spécifiée.|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Retourne l’instance de module à partir d’un `CAtlBaseModule` objet.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Retourne l’instance de la ressource à partir d’un `CAtlBaseModule` objet.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Supprime une instance de ressource dans la liste des handles stockées.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Définit l’instance de ressource d’un `CAtlBaseModule` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Une variable qui indique si l’initialisation du module a échoué.|  
  
## <a name="remarks"></a>Notes  
 Une instance de `CAtlBaseModule` _AtlBaseModule nommé est présent dans chaque projet ATL, qui contient un handle vers l’instance de module, un handle vers le module qui contient les ressources (par défaut, sont les mêmes) et un tableau de handles aux modules fournissant principal ressources. `CAtlBaseModule` rendre accessible à partir de plusieurs threads.  
  
 Cette classe remplace l’obsolète [CComModule](../../atl/reference/ccommodule-class.md) classe utilisée dans les versions antérieures d’ATL.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance  
 Ajoute une instance de la ressource à la liste des handles stockées.  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hInst`  
 L’instance de la ressource à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la ressource a été correctement ajouté, false dans le cas contraire.  
  
##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule  
 Constructeur.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Notes  
 Crée l'objet `CAtlBaseModule`.  
  
##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt  
 Retourne un handle vers une instance de la ressource spécifiée.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *i*  
 Le numéro de l’instance de la ressource.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle vers l’instance de la ressource, ou NULL si aucune instance de ressource correspondant n’existe.  
  
##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance  
 Retourne l’instance de module à partir d’un `CAtlBaseModule` objet.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’instance de module.  
  
##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance  
 Retourne l’instance de ressource.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’instance de ressource.  
  
##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed  
 Une variable qui indique si l’initialisation du module a échoué.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Notes  
 True si le module est initialisé, false en cas d’échec d’initialisation.  
  
##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance  
 Supprime une instance de ressource dans la liste des handles stockées.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hInst`  
 L’instance de la ressource à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la ressource a été supprimée avec succès.  
  
##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance  
 Définit l’instance de ressource d’un `CAtlBaseModule` objet.  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hInst`  
 La nouvelle instance de la ressource.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’instance de la ressource mise à jour.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)
