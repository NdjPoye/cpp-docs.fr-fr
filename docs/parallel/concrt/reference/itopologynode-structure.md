---
title: ITopologyNode (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: c0a4e8365d7d0ef9912bb84e4a2a4cfe7e9ef0f1
ms.lasthandoff: 03/17/2017

---
# <a name="itopologynode-structure"></a>ITopologyNode, structure
Interface avec un nœud de topologie, comme défini par le gestionnaire des ressources. Un nœud contient une ou plusieurs ressources d'exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|Retourne le nombre de ressources d’exécution regroupés sous ce nœud.|  
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|Retourne la première ressource d’exécution regroupée sous ce nœud dans l’ordre d’énumération.|  
|[ITopologyNode::GetId](#getid)|Retourne l’identificateur unique du Gestionnaire de ressources pour ce nœud.|  
|[ITopologyNode::GetNext](#getnext)|Retourne une interface pour le nœud de topologie suivant dans l’ordre d’énumération.|  
|[ITopologyNode::GetNumaNode](#getnumanode)|Retourne les fenêtres attribué numéro de nœud NUMA auquel appartient ce nœud du Gestionnaire de ressources.|  
  
## <a name="remarks"></a>Remarques  
 Cette interface est généralement utilisée pour parcourir la topologie du système comme observée par le Gestionnaire de ressources.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ITopologyNode`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="getexecutionresourcecount"></a>Itopologynode::getexecutionresourcecount, méthode  
 Retourne le nombre de ressources d’exécution regroupés sous ce nœud.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de ressources d’exécution sont regroupés sous ce nœud.  
  
##  <a name="getfirstexecutionresource"></a>Itopologynode::getfirstexecutionresource, méthode  
 Retourne la première ressource d’exécution regroupée sous ce nœud dans l’ordre d’énumération.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première ressource d’exécution sont regroupés sous ce nœud dans l’ordre d’énumération.  
  
##  <a name="getid"></a>Itopologynode::GetId, méthode  
 Retourne l’identificateur unique du Gestionnaire de ressources pour ce nœud.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur unique du Gestionnaire de ressources pour ce nœud.  
  
### <a name="remarks"></a>Remarques  
 Le Runtime d’accès concurrentiel représente des threads matériels sur le système dans des groupes de nœuds processeur. Nœuds sont dérivés habituellement de la topologie de matériel du système. Par exemple, tous les processeurs sur un socket spécifique ou un nœud NUMA spécifique peuvent appartenir au même nœud du processeur. Le Gestionnaire des ressources assigne des identificateurs uniques à ces nœuds en commençant à `0` de `nodeCount - 1`, où `nodeCount` représente le nombre total de nœuds processeur sur le système.  
  
 Le nombre de nœuds peut être obtenu à partir de la fonction [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="getnext"></a>Itopologynode::GetNext, méthode  
 Retourne une interface pour le nœud de topologie suivant dans l’ordre d’énumération.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une interface vers le nœud suivant dans l’ordre d’énumération. S’il n’y a pas d’autres nœuds dans l’ordre d’énumération de la topologie du système, cette méthode retourne la valeur `NULL`.  
  
##  <a name="getnumanode"></a>Itopologynode::getnumanode, méthode  
 Retourne les fenêtres attribué numéro de nœud NUMA auquel appartient ce nœud du Gestionnaire de ressources.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Windows attribué un numéro de nœud NUMA auquel appartient ce nœud du Gestionnaire de ressources.  
  
### <a name="remarks"></a>Remarques  
 Un proxy de thread en cours d’exécution sur une racine de processeur virtuel appartenant à ce nœud aura une affinité au moins au niveau du nœud NUMA du nœud NUMA retourné par cette méthode.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

