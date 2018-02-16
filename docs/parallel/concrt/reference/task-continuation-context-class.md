---
title: task_continuation_context, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b78688493bbb8d8bdad0696a7c8fcf467519000
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context, classe
La classe `task_continuation_context` vous permet de spécifier où vous souhaitez qu'une continuation soit exécutée. Il n’est utile d’utiliser cette classe à partir d’une application Windows Runtime. Pour les applications non Windows Runtime, le contexte d’exécution de la continuation de tâche est déterminé par le runtime et n’est pas configurable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Retourne un objet de contexte de continuation de tâche qui représente le contexte actuel du thread winrt.|  
|[use_arbitrary](#use_arbitrary)|Crée un contexte de continuation de tâche qui permet au runtime de choisir le contexte d’exécution pour une continuation.|  
|[use_current](#use_current)|Renvoie un objet de contexte de continuation de tâche représentant le contexte d’exécution actuel.|  
|[use_default](#use_default)|Crée le contexte de continuation de tâche par défaut.|  
|[use_synchronous_execution](#use_synchronous_execution)|Retourne un objet de contexte de continuation de tâche qui représente le contexte de l’exécution synchrone.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  

## <a name="get_current_winrt_context"></a> get_current_winrt_context
 Retourne un objet de contexte de continuation de tâche qui représente le contexte actuel du thread WinRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le contexte actuel du thread Windows Runtime. Retourne un task_continuation_context vide si elle est appelée à partir d’un contexte non Windows Runtime.  
  
## <a name="remarks"></a>Notes  
 Le `get_current_winrt_context` méthode capture le contexte de thread Windows Runtime de l’appelant. Elle retourne un contexte vide à des appelants non Windows Runtime.  
  
 La valeur retournée par `get_current_winrt_context` peut être utilisé pour indiquer à l’exécution que la continuation doit s’exécuter dans le modèle de cloisonnement du contexte capturé (STA et MTA), indépendamment de si la tâche antécédente est cloisonné prenant en charge. Un thread cloisonné prenant en charge les tâches sont une tâche qui se désencapsule un objet Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche.  
  
 Cette méthode est similaire à la `use_current` (méthode), mais il est également disponible pour le code C++ natif sans C + c++ / prise en charge des extensions CX. Il est destiné aux utilisateurs avancés utilisé par l’écriture C + c++ / CX bibliothèque code d’indépendant natif et les appelants de Windows Runtime. Sauf si vous avez besoin de cette fonctionnalité, nous vous recommandons du `use_current` (méthode), qui est uniquement disponible pour C + c++ / les clients CX.  
  
  
##  <a name="use_arbitrary"></a> use_arbitrary 

 Crée un contexte de continuation de tâche qui permet au runtime de choisir le contexte d’exécution pour une continuation.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un contexte de continuation de tâche qui représente un emplacement arbitraire.  
  
### <a name="remarks"></a>Notes  
 Lorsque ce contexte de continuation est utilisé, la continuation s’exécute dans un contexte, que le runtime sélectionne même si la tâche antécédente est cloisonné prenant en charge.  
  
 `use_arbitrary` peut être utilisé pour désactiver le comportement par défaut pour une continuation sur une tâche prenant en charge de cloisonnement créée dans un STA.  
  
 Cette méthode est uniquement disponible pour les applications Windows Runtime.  
  
##  <a name="use_current"></a> use_current 

 Renvoie un objet de contexte de continuation de tâche représentant le contexte d’exécution actuel.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Contexte d'exécution actuel.  
  
### <a name="remarks"></a>Notes  
 Cette méthode capture le contexte d’exécution de Windows de l’appelant afin que les continuations peuvent être exécutées dans le compartiment de droite.  
  
 La valeur retournée par `use_current` peut être utilisé pour indiquer à l’exécution que la continuation doit s’exécuter dans le contexte capturé (STA et MTA), même si la tâche antécédente cloisonnement prenant en charge. Un thread cloisonné prenant en charge les tâches sont une tâche qui se désencapsule un objet Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche.  
  
 Cette méthode est uniquement disponible pour les applications Windows Runtime.  
  
##  <a name="use_default"></a> use_default 

 Crée le contexte de continuation de tâche par défaut.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le contexte de continuation par défaut.  
  
### <a name="remarks"></a>Notes  
 Le contexte par défaut est utilisé si vous ne spécifiez pas un contexte de continuation lorsque vous appelez le `then` (méthode). Dans les applications Windows pour Windows 7 et en dessous, ainsi que les applications de bureau sous Windows 8 et versions ultérieures, le runtime détermine où les continuations de tâches seront exécute. Toutefois, dans une application Windows Runtime, le contexte de continuation par défaut pour une continuation sur une tâche prenant en charge de cloisonnement est le cloisonnement où `then` est appelé.  
  
 Un thread cloisonné prenant en charge les tâches sont une tâche qui se désencapsule un objet Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche. Par conséquent, si vous planifiez une continuation sur une tâche prenant en charge de cloisonnement dans un STA d’exécution de Windows, la continuation s’exécute dans ce STA.  
  
 Une continuation sur une tâche prenant en charge un cloisonnement non s’exécute dans un contexte, que le Runtime sélectionne.  

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution  
Retourne un objet de contexte de continuation de tâche qui représente le contexte de l’exécution synchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le contexte de l’exécution synchrone.  
  
## <a name="remarks"></a>Notes  
 Le `use_synchronous_execution` méthode force la tâche de continuation à exécuter simultanément sur le contexte, à l’origine de la fin de la sa tâche antécédente.  
  
 Si l’antécédent est déjà terminée lorsque la continuation est jointe, la continuation s’exécute de façon synchrone sur le contexte qui joint la continuation.  
  
 
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
