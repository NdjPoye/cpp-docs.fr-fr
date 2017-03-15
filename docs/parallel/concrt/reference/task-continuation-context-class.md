---
title: task_continuation_context, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_continuation_context
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 627c2adc60c143ef7cd9be62f71a4365eed5aed5
ms.lasthandoff: 02/24/2017

---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context, classe
La classe `task_continuation_context` vous permet de spécifier où vous souhaitez qu'une continuation soit exécutée. Seule l'utilisation de cette classe à partir d'une application du Windows Store s'avère utile. Pour les applications qui ne figurent pas dans le Windows Store, le contexte d’exécution de la continuation de tâche est déterminé par le runtime et n’est pas configurable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_current_winrt_context (méthode)](#get_current_winrt_context)|Retourne un objet de contexte de continuation de tâche qui représente le contexte actuel du thread winrt.|  
|[use_arbitrary (méthode)](#use_arbitrary)|Crée un contexte de continuation de tâche qui permet au runtime de choisir le contexte d’exécution pour une continuation.|  
|[use_current (méthode)](#use_current)|Renvoie un objet de contexte de continuation de tâche représentant le contexte d’exécution actuel.|  
|[use_default (méthode)](#use_default)|Crée le contexte de continuation de tâche par défaut.|  
|[use_synchronous_execution (méthode)](#use_synchronous_execution)|Retourne un objet de contexte de continuation de tâche qui représente le contexte de l’exécution synchrone.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  

## <a name="a-namegetcurrentwinrtcontexta-getcurrentwinrtcontext"></a><a name="get_current_winrt_context"></a>get_current_winrt_context
 Retourne un objet de contexte de continuation de tâche qui représente le contexte actuel du thread WinRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le contexte actuel du thread Windows Runtime. Retourne un task_continuation_context vide si elle est appelée à partir d’un contexte non Windows Runtime.  
  
## <a name="remarks"></a>Remarques  
 Le `get_current_winrt_context` méthode capture le contexte de thread de l’appelant de l’exécution de Windows. Elle retourne un contexte vide pour les appelants non Windows Runtime.  
  
 La valeur retournée par `get_current_winrt_context` peut être utilisé pour indiquer à l’exécution que la continuation doit s’exécuter dans le modèle de cloisonnement du contexte capturé (STA et MTA), indépendamment de si l’antécédent est cloisonné prenant en charge. Un thread cloisonné prenant en charge les tâches est une tâche désencapsule une Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche.  
  
 Cette méthode est similaire à la `use_current` (méthode), mais il est également disponible en code C++ natif sans C + c++ / prise en charge des extensions CX. Il est prévu pour utilisation par écriture C + utilisateurs avancés c++ / code de bibliothèque de natif et Windows Runtime appelants CX indépendant. Sauf si vous avez besoin de cette fonctionnalité, nous vous recommandons du `use_current` (méthode), qui est uniquement disponible pour C + c++ / les clients CX.  
  
  
##  <a name="a-nameusearbitrarya-usearbitrary"></a><a name="use_arbitrary"></a>use_arbitrary 

 Crée un contexte de continuation de tâche qui permet au runtime de choisir le contexte d’exécution pour une continuation.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un contexte de continuation de tâche qui représente un emplacement arbitraire.  
  
### <a name="remarks"></a>Remarques  
 Lorsque ce contexte de continuation est utilisé la continuation s’exécutent dans un contexte, que le runtime sélectionne même si l’antécédent est un modèle apartment prenant en charge.  
  
 `use_arbitrary`peut être utilisé pour désactiver le comportement par défaut pour une liaison dans une tâche prenant en charge de cloisonnement créée dans un STA.  
  
 Cette méthode est uniquement disponible pour les applications du Windows Store.  
  
##  <a name="a-nameusecurrenta-usecurrent"></a><a name="use_current"></a>use_current 

 Renvoie un objet de contexte de continuation de tâche représentant le contexte d’exécution actuel.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Contexte d'exécution actuel.  
  
### <a name="remarks"></a>Notes  
 Cette méthode capture le contexte d’exécution de Windows de l’appelant afin que les continuations peuvent être exécutées dans le compartiment de droite.  
  
 La valeur retournée par `use_current` peut être utilisé pour indiquer à l’exécution que la continuation doit s’exécuter dans le contexte capturé (STA et MTA), quelle que soit ou non l’antécédent est un modèle apartment prenant en charge. Un thread cloisonné prenant en charge les tâches est une tâche désencapsule une Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche.  
  
 Cette méthode est uniquement disponible pour les applications du Windows Store.  
  
##  <a name="a-nameusedefaulta-usedefault"></a><a name="use_default"></a>use_default 

 Crée le contexte de continuation de tâche par défaut.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le contexte de continuation par défaut.  
  
### <a name="remarks"></a>Notes  
 Le contexte par défaut est utilisé si vous ne spécifiez pas un contexte de continuation lorsque vous appelez le `then` (méthode). Dans les applications Windows pour Windows 7 et en dessous, ainsi que des applications de bureau sur Windows 8 et versions ultérieures, le runtime détermine où les continuations de tâches seront exécutée. Toutefois, dans une application Windows Store, le contexte de continuation par défaut pour une liaison dans une tâche prenant en charge de cloisonnement est le cloisonnement où `then` est appelé.  
  
 Un thread cloisonné prenant en charge les tâches est une tâche désencapsule une Windows Runtime `IAsyncInfo` interface ou une tâche qui est issue de ce type de tâche. Par conséquent, si vous planifiez une continuation sur une tâche prenant en charge de cloisonnement dans un STA d’exécution de Windows, la continuation exécute dans ce STA.  
  
 Une continuation d’une tâche prenant en charge un cloisonnement non s’exécuter dans un contexte que choisit le Runtime.  

## <a name="a-nameusesynchronousexecutiona-taskcontinuationcontextusesynchronousexecution"></a><a name="use_synchronous_execution"></a>task_continuation_context::use_synchronous_execution  
Retourne un objet de contexte de continuation de tâche qui représente le contexte de l’exécution synchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Le contexte d’exécution synchrone.  
  
## <a name="remarks"></a>Notes  
 Le `use_synchronous_execution` méthode force la tâche de continuation à exécuter simultanément sur le contexte, à l’origine de la saisie semi-automatique de son antécédent.  
  
 Si l’antécédent est déjà terminé lorsque la continuation est attachée, la continuation s’exécute de façon synchrone sur le contexte qui attache la continuation.  
  
 
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

