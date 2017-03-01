---
title: IUMSThreadProxy (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSThreadProxy
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 55ed05f137775e819c81ce231cf8c8ad3a9974f3
ms.lasthandoff: 02/24/2017

---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy, structure
Abstraction d'un thread d'exécution. Si vous voulez que votre planificateur reçoive des threads UMS (User-Mode Scheduling), affectez à l'élément de stratégie du planificateur `SchedulerKind` la valeur `UmsThreadDefault`, puis implémentez l'interface `IUMSScheduler`. Les threads UMS sont uniquement pris en charge sur les systèmes d'exploitation 64 bits avec Windows 7 et ses versions ultérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IUMSThreadProxy::EnterCriticalRegion, méthode](#entercriticalregion)|Appelé pour accéder à une zone critique. À l’intérieur d’une zone critique, le planificateur ne sera pas équilibrée des opérations de blocage asynchrones qui peut se produisent au cours de la région. Cela signifie que le planificateur ne sera pas être réintroduite de défauts de page, arrêts de thread, les appels de procédure asynchrone du noyau (APC), etc., pour un thread UMS.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion, méthode](#enterhypercriticalregion)|Appelé pour accéder à une région hyper critique. Dans une région hyper-critique, le planificateur ne sera pas équilibrée des opérations de blocage qui se produisent lors de la région. Cela signifie que le planificateur ne sera pas réentré pour bloquer les appels de fonction, les tentatives d’acquisition de verrou qui se bloquent, défauts de page, thread suspensions, appels de procédure asynchrone de noyau (APC) et ainsi de suite, pour un UMS thread.|  
|[IUMSThreadProxy::ExitCriticalRegion, méthode](#exitcriticalregion)|Appelé pour quitter une région critique.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion, méthode](#exithypercriticalregion)|Appelé pour quitter une région hyper critique.|  
|[IUMSThreadProxy::GetCriticalRegionType, méthode](#getcriticalregiontype)|Retourne le type de région critique, le proxy de thread se trouve dans. Étant donné que Hyper-critiques sont un sur-ensemble de régions critiques, si le code a entré une région critique, puis une région hyper-critique, `InsideHyperCriticalRegion` sera retourné.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrtrm.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameentercriticalregiona--iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>IUMSThreadProxy::EnterCriticalRegion, méthode  
 Appelé pour accéder à une zone critique. À l’intérieur d’une zone critique, le planificateur ne sera pas équilibrée des opérations de blocage asynchrones qui peut se produisent au cours de la région. Cela signifie que le planificateur ne sera pas être réintroduite de défauts de page, arrêts de thread, les appels de procédure asynchrone du noyau (APC), etc., pour un thread UMS.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvelle profondeur de la région critique. Les régions critiques sont réentrantes.  
  
##  <a name="a-nameenterhypercriticalregiona--iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>IUMSThreadProxy::EnterHyperCriticalRegion, méthode  
 Appelé pour accéder à une région hyper critique. Dans une région hyper-critique, le planificateur ne sera pas équilibrée des opérations de blocage qui se produisent lors de la région. Cela signifie que le planificateur ne sera pas réentré pour bloquer les appels de fonction, les tentatives d’acquisition de verrou qui se bloquent, défauts de page, thread suspensions, appels de procédure asynchrone de noyau (APC) et ainsi de suite, pour un UMS thread.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvelle profondeur de la région hyper critique. Les régions Hyper critiques sont réentrantes.  
  
### <a name="remarks"></a>Remarques  
 Le planificateur doit être extraordinairement prudent concernant ce que les méthodes il appelle et quels verrous il acquiert dans ces régions. Si le code dans une région de ce type se bloque sur un verrou est détenu par quelque chose sur que le planificateur est chargé de planifier, blocage peut-être survenir.  
  
##  <a name="a-nameexitcriticalregiona--iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>IUMSThreadProxy::ExitCriticalRegion, méthode  
 Appelé pour quitter une région critique.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvelle profondeur de la région critique. Les régions critiques sont réentrantes.  
  
##  <a name="a-nameexithypercriticalregiona--iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>IUMSThreadProxy::ExitHyperCriticalRegion, méthode  
 Appelé pour quitter une région hyper critique.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvelle profondeur de la région hyper critique. Les régions Hyper critiques sont réentrantes.  
  
##  <a name="a-namegetcriticalregiontypea--iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>IUMSThreadProxy::GetCriticalRegionType, méthode  
 Retourne le type de région critique, le proxy de thread se trouve dans. Étant donné que Hyper-critiques sont un sur-ensemble de régions critiques, si le code a entré une région critique, puis une région hyper-critique, `InsideHyperCriticalRegion` sera retourné.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Type de région critique, dans que le proxy de thread se trouve.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [IUMSScheduler (Structure)](iumsscheduler-structure.md)

