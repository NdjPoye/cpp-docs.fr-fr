---
title: Classe de CAtlBaseModule | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlBaseModule
- ATL.CAtlBaseModule
- CAtlBaseModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
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
ms.openlocfilehash: 4897f6cf7e12a18401720ad663c90491bb0e599d
ms.lasthandoff: 02/24/2017

---
# <a name="catlbasemodule-class"></a>CAtlBaseModule (classe)
Cette classe est instanciée dans tous les projets ATL.  
  
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
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Retourne l’instance de module d’un `CAtlBaseModule` objet.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Retourne l’instance de ressource d’un `CAtlBaseModule` objet.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Supprime une instance de la ressource dans la liste des handles stockées.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Définit l’instance de ressource d’un `CAtlBaseModule` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Une variable qui indique si l’initialisation du module a échoué.|  
  
## <a name="remarks"></a>Notes  
 Une instance de `CAtlBaseModule` nommée _AtlBaseModule est présent dans chaque projet ATL, qui contient un pointeur vers l’instance de module, un handle vers le module qui contient les ressources (par défaut, sont les mêmes) et un tableau de handles vers des modules de ressources principal. `CAtlBaseModule`est accessible en toute sécurité à partir de plusieurs threads.  
  
 Cette classe remplace obsolète [CComModule](../../atl/reference/ccommodule-class.md) classe utilisée dans les versions antérieures de l’ATL.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="a-nameaddresourceinstancea--catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance  
 Ajoute une instance de la ressource à la liste des handles stockées.  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hInst`  
 L’instance de la ressource à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la ressource a été ajouté, false dans le cas contraire.  
  
##  <a name="a-namecatlbasemodulea--catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule  
 Constructeur.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Crée l'objet `CAtlBaseModule`.  
  
##  <a name="a-namegethinstanceata--catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt  
 Retourne un handle vers une instance de la ressource spécifiée.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *i*  
 Le numéro de l’instance de la ressource.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle de l’instance de la ressource, ou NULL si aucune instance de ressource correspondante n’existe.  
  
##  <a name="a-namegetmoduleinstancea--catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance  
 Retourne l’instance de module d’un `CAtlBaseModule` objet.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’instance du module.  
  
##  <a name="a-namegetresourceinstancea--catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance  
 Retourne l’instance de ressource.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’instance de ressource.  
  
##  <a name="a-namembinitfaileda--catlbasemodulembinitfailed"></a><a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed  
 Une variable qui indique si l’initialisation du module a échoué.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Notes  
 True si le module est initialisé, false en cas d’échec d’initialisation.  
  
##  <a name="a-nameremoveresourceinstancea--catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance  
 Supprime une instance de la ressource dans la liste des handles stockées.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `hInst`  
 L’instance de la ressource à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si la ressource a été supprimée avec succès.  
  
##  <a name="a-namesetresourceinstancea--catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance  
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

