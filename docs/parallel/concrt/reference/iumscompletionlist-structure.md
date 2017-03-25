---
title: IUMSCompletionList (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 65655e4e03a7b187e0bbadbd576bc088bb57f7c8
ms.lasthandoff: 03/17/2017

---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList, structure
Représente une liste de saisie semi-automatique UMS. Quand un thread UMS se bloque, le contexte de planification désigné du planificateur est distribué afin de déterminer les éléments à planifier sur la racine du processeur virtuel sous-jacent pendant que le thread d'origine est bloqué. Quand le thread d'origine se débloque, le système d'exploitation le met en attente dans la liste de saisie semi-automatique accessible via cette interface. Le planificateur peut interroger la liste de saisie semi-automatique à propos du contexte de planification désigné ou de tout autre emplacement qu'il recherche pour du travail.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Récupère une chaîne de `IUMSUnblockNotification` les interfaces qui représentent des contextes d’exécution dont le thread associé proxys se sont débloqués depuis le dernier appel de la méthode a été appelé.|  
  
## <a name="remarks"></a>Notes  
 Un planificateur doit être extraordinairement prudent concernant les actions à effectuer après avoir utilisé cette interface pour la file d’attente des éléments de la liste de saisie semi-automatique. Les éléments doivent être placés sur la liste du Planificateur de contextes exécutables et être généralement accessible dès que possible. Il est tout à fait possible qu’un des éléments retirés de l’a reçu la propriété d’un verrou arbitraire. Le planificateur ne peut effectuer aucun appel de fonction arbitraires qui peuvent se bloquer entre l’appel à des éléments de la file d’attente et le positionnement de ces éléments dans une liste qui sont généralement accessibles à partir du planificateur.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="getunblocknotifications"></a>IUMSCompletionList::GetUnblockNotifications, méthode  
 Récupère une chaîne de `IUMSUnblockNotification` les interfaces qui représentent des contextes d’exécution dont le thread associé proxys se sont débloqués depuis le dernier appel de la méthode a été appelé.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une chaîne de `IUMSUnblockNotification` interfaces.  
  
### <a name="remarks"></a>Remarques  
 Les notifications retournées ne sont pas valides une fois que les contextes d’exécution sont replanifiées.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [IUMSScheduler (Structure)](iumsscheduler-structure.md)   
 [IUMSUnblockNotification, structure](iumsunblocknotification-structure.md)

