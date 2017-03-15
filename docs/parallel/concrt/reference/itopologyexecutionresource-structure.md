---
title: ITopologyExecutionResource (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ITopologyExecutionResource
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: cc54beb4790c9d2ea5bfcb2c8ffd4bca7dca399e
ms.lasthandoff: 02/24/2017

---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource, structure
Interface avec une ressource d'exécution tel que défini par le Gestionnaire de ressources.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Itopologyexecutionresource::GetId, méthode](#getid)|Retourne l’identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.|  
|[Itopologyexecutionresource::GetNext, méthode](#getnext)|Retourne une interface pour la ressource d’exécution suivante dans l’ordre d’énumération.|  
  
## <a name="remarks"></a>Notes  
 Cette interface est généralement utilisée pour parcourir la topologie du système comme observée par le Gestionnaire de ressources.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namegetida--itopologyexecutionresourcegetid-method"></a><a name="getid"></a>Itopologyexecutionresource::GetId, méthode  
 Retourne l’identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.  
  
##  <a name="a-namegetnexta--itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>Itopologyexecutionresource::GetNext, méthode  
 Retourne une interface pour la ressource d’exécution suivante dans l’ordre d’énumération.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Interface pour la ressource d’exécution suivante dans l’ordre d’énumération. S’il n’y a pas d’autres nœuds dans l’ordre d’énumération du nœud auquel appartient cette ressource d’exécution, cette méthode retourne la valeur `NULL`.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

