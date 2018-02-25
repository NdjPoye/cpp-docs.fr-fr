---
title: Itopologyexecutionresource, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9b044575fdaccead8c30bd8dca955923a8c5f9e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
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
|[ITopologyExecutionResource::GetId](#getid)|Retourne l’identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.|  
|[ITopologyExecutionResource::GetNext](#getnext)|Retourne une interface pour la ressource de l’exécution suivante dans l’ordre d’énumération.|  
  
## <a name="remarks"></a>Notes  
 Cette interface est généralement utilisée pour parcourir la topologie du système comme observée par le Gestionnaire de ressources.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="getid"></a>  Itopologyexecutionresource::GetId, méthode  
 Retourne l’identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique du Gestionnaire de ressources pour cette ressource d’exécution.  
  
##  <a name="getnext"></a>  Itopologyexecutionresource::GetNext, méthode  
 Retourne une interface pour la ressource de l’exécution suivante dans l’ordre d’énumération.  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une interface à la ressource de l’exécution suivante dans l’ordre d’énumération. S’il n’y a pas d’autres nœuds dans l’ordre d’énumération du nœud auquel appartient cette ressource d’exécution, cette méthode retourne la valeur `NULL`.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
