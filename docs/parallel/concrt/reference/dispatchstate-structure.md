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
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a617d1f1d7f68c00c7011daffc6ba59f08c43a1e
ms.lasthandoff: 03/17/2017

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
|[DispatchState::DispatchState](#ctor)|Construit un nouveau `DispatchState` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Taille de cette structure, qui est utilisée pour le contrôle de version.|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Indique si ce contexte a entré le `Dispatch` méthode parce que le contexte précédent bloqué de façon asynchrone. Cela est utilisé uniquement dans le contexte de planification UMS et est défini sur la valeur `0` pour tous les autres contextes d’exécution.|  
|[DispatchState::m_reserved](#m_reserved)|Bits réservés pour le passage de futures informations.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `DispatchState`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>DispatchState::DispatchState, constructeur  
 Construit un nouveau `DispatchState` objet.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>Données membres DispatchState::m_dispatchStateSize  
 Taille de cette structure, qui est utilisée pour le contrôle de version.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>Données membres DispatchState::m_fIsPreviousContextAsynchronouslyBlocked  
 Indique si ce contexte a entré le `Dispatch` méthode parce que le contexte précédent bloqué de façon asynchrone. Cela est utilisé uniquement dans le contexte de planification UMS et est défini sur la valeur `0` pour tous les autres contextes d’exécution.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>Données membres DispatchState::m_reserved  
 Bits réservés pour le passage de futures informations.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

