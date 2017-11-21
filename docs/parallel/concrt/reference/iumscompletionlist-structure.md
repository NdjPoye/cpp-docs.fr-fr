---
title: IUMSCompletionList, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs: C++
helpviewer_keywords: IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: df3bb5be4f2032353dd08e551591a03cdc2f4b17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Récupère une chaîne de `IUMSUnblockNotification` les interfaces qui représentent des contextes d’exécution dont le thread associé proxys ont été débloqués depuis la dernière exécution de cette méthode a été appelé.|  
  
## <a name="remarks"></a>Remarques  
 Un planificateur doit être extrêmement prudent lorsque vous les actions à effectuer après l’utilisation de cette interface pour enlever les éléments à partir de la liste de saisie semi-automatique. Les éléments doivent être placés sur la liste du Planificateur de contextes exécutables et être généralement accessibles dès que possible. Il est tout à fait possible qu’un des éléments des file d’attente ait reçu la propriété d’un verrou arbitraire. Le planificateur ne peut effectuer aucun appel de fonction arbitraires qui peuvent se bloquer entre l’appel des éléments de la file d’attente et le placement de ces éléments dans une liste qui sont généralement accessibles à partir du planificateur.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="getunblocknotifications"></a>IUMSCompletionList::GetUnblockNotifications, méthode  
 Récupère une chaîne de `IUMSUnblockNotification` les interfaces qui représentent des contextes d’exécution dont le thread associé proxys ont été débloqués depuis la dernière exécution de cette méthode a été appelé.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une chaîne de `IUMSUnblockNotification` interfaces.  
  
### <a name="remarks"></a>Remarques  
 Les notifications retournées ne sont pas valides une fois que les contextes d’exécution sont replanifiés.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [IUMSScheduler, Structure](iumsscheduler-structure.md)   
 [IUMSUnblockNotification, structure](iumsunblocknotification-structure.md)
