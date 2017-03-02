---
title: DispatchState (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::DispatchState
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
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
ms.openlocfilehash: 46c2219464e57da4931596e970199549405d02ec
ms.lasthandoff: 02/24/2017

---
# <a name="dispatchstate-structure"></a>DispatchState, structure
La structure `DispatchState` est utilisée pour transférer l'état à la méthode `IExecutionContext::Dispatch`. Elle décrit les circonstances dans lesquelles la méthode `Dispatch` est appelée sur une interface `IExecutionContext`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[DispatchState::DispatchState, constructeur](#ctor)|Construit un nouveau `DispatchState` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Données membres DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Taille de cette structure, qui est utilisée pour le contrôle de version.|  
|[Données membres DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Indique si ce contexte a entré le `Dispatch` méthode parce que le contexte précédent bloqué de façon asynchrone. Cela est utilisé uniquement dans le contexte de planification UMS et est défini sur la valeur `0` pour tous les autres contextes d’exécution.|  
|[Données membres DispatchState::m_reserved](#m_reserved)|Bits réservés pour le passage de futures informations.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `DispatchState`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namectora--dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>DispatchState::DispatchState, constructeur  
 Construit un nouveau `DispatchState` objet.  
  
```
DispatchState();
```  
  
##  <a name="a-namemdispatchstatesizea--dispatchstatemdispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>Données membres DispatchState::m_dispatchStateSize  
 Taille de cette structure, qui est utilisée pour le contrôle de version.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="a-namemfispreviouscontextasynchronouslyblockeda--dispatchstatemfispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>Données membres DispatchState::m_fIsPreviousContextAsynchronouslyBlocked  
 Indique si ce contexte a entré le `Dispatch` méthode parce que le contexte précédent bloqué de façon asynchrone. Cela est utilisé uniquement dans le contexte de planification UMS et est défini sur la valeur `0` pour tous les autres contextes d’exécution.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="a-namemreserveda--dispatchstatemreserved-data-member"></a><a name="m_reserved"></a>Données membres DispatchState::m_reserved  
 Bits réservés pour le passage de futures informations.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

