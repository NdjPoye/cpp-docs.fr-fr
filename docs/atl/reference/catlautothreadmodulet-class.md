---
title: Classe de CAtlAutoThreadModuleT | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 082214794b2caa66e8be1127c664e0ffec18a394
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="catlautothreadmodulet-class"></a>Classe de CAtlAutoThreadModuleT
Cette classe fournit des méthodes pour implémenter un serveur COM mis en pool de threads, le modèle de cloisonnement.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 La classe qui implémentera le serveur COM.  
  
 `ThreadAllocator`  
 La classe de la gestion de sélection de thread. La valeur par défaut est [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Spécifie l’intervalle de délai d’attente, en millisecondes. La valeur par défaut est INFINITE, ce qui signifie intervalle de délai d’attente de la méthode jamais à expiration.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Cette fonction statique dynamiquement calcule et retourne le nombre maximal de threads pour le module EXE, en fonction du nombre de processeurs.|  
  
## <a name="remarks"></a>Notes  
 La classe [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) dérive `CAtlAutoThreadModuleT` pour implémenter un serveur COM mis en pool de threads, le modèle de cloisonnement. Il remplace la classe obsolète [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Cette classe ne doit pas être utilisée dans une DLL, comme la valeur par défaut `dwWait` valeur INFINITE entraîne un blocage lors de la DLL est déchargée.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Cette fonction statique dynamiquement calcule et retourne le nombre maximal de threads pour le module EXE, en fonction du nombre de processeurs.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de threads à créer dans le module EXE.  
  
### <a name="remarks"></a>Notes  
 Substituez cette méthode si vous souhaitez utiliser une autre méthode pour calculer le nombre de threads. Par défaut, le nombre de threads est basé sur le nombre de processeurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Classe de IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)
