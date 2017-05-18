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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 86b35f0a6a3ab43c170ee710838ec9ba0e2fc5b0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT (classe)
Cette classe fournit des méthodes pour implémenter un pool de threads cloisonnés COM serveur.  
  
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
 La classe qui implémente le serveur COM.  
  
 `ThreadAllocator`  
 La classe de la gestion de sélection de thread. La valeur par défaut est [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Spécifie l’intervalle de délai d’attente, en millisecondes. La valeur par défaut est INFINITE, ce qui signifie que le délai d’utilisation de la méthode jamais est écoulé.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Cette fonction statique dynamiquement calcule et retourne le nombre maximal de threads pour le module EXE, en fonction du nombre de processeurs.|  
  
## <a name="remarks"></a>Remarques  
 La classe [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) dérive `CAtlAutoThreadModuleT` afin d’implémenter un pool de threads cloisonnés COM serveur. Il remplace la classe obsolète [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Cette classe ne doit pas être utilisée dans une DLL, comme la valeur par défaut `dwWait` valeur INFINITE provoque un blocage lors de la DLL est déchargée.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Cette fonction statique dynamiquement calcule et retourne le nombre maximal de threads pour le module EXE, en fonction du nombre de processeurs.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de threads doit être créé dans le module du fichier EXE.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode si vous souhaitez utiliser une autre méthode pour calculer le nombre de threads. Par défaut, le nombre de threads est basé sur le nombre de processeurs.  
  
## <a name="see-also"></a>Voir aussi  
 [IAtlAutoThreadModule (classe)](../../atl/reference/iatlautothreadmodule-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule (classe)](../../atl/reference/iatlautothreadmodule-class.md)   
 [Module (Classes)](../../atl/atl-module-classes.md)

