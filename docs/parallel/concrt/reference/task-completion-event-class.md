---
title: task_completion_event, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
dev_langs: C++
helpviewer_keywords: task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78c5cb9bdd1da0876abacda48000a914c884d25a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="taskcompletionevent-class"></a>task_completion_event, classe
La classe `task_completion_event` vous permet de retarder l'exécution d'une tâche jusqu'à ce qu'une condition soit satisfaite, ou de démarrer une tâche en réponse à un événement externe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_ResultType`  
 Type de résultat de cette classe `task_completion_event`.  
  
 `T`  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[task_completion_event](#ctor)|Construit un objet `task_completion_event`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[set](#set)|Surchargé. Définit l’événement de fin de tâche.|  
|[set_exception](#set_exception)|Surchargé. Propage une exception à toutes les tâches associées à cet événement.|  
  
## <a name="remarks"></a>Remarques  
 Utilisez une tâche créée à partir d’un événement de fin de tâche quand votre scénario vous oblige à créer une tâche qui va se terminer. La continuation de son exécution est ainsi planifiée, à un moment donné dans le futur. Le `task_completion_event` doit avoir le même type que la tâche que vous créez et l'appel de la méthode set sur l'événement de fin de tâche avec une valeur de ce type entraîne la fin de tâche associée et fournit cette valeur comme résultat de la continuation de la tâche.  
  
 Si l'événement de fin de tâche n'est jamais signalé, toutes les tâches créées à partir de celle-ci seront annulées durant sa destruction.  
  
 `task_completion_event` se comporte comme un pointeur intelligent et doit être passé par valeur.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `task_completion_event`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="set"></a>ensemble 

 Définit l’événement de fin de tâche.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Result`  
 Le résultat pour définir cet événement.  
  
### <a name="return-value"></a>Valeur de retour  
 La méthode retourne `true` si elle a réussi dans la définition de l’événement. Elle retourne `false` si l’événement est déjà défini.  
  
### <a name="remarks"></a>Remarques  
 En présence de plusieurs ou d’appels simultanés à `set`, seul le premier appel réussi et que son résultat (le cas échéant) est stocké dans l’événement d’achèvement de tâche. Les jeux restants sont ignorés et la méthode retourne la valeur false. Lorsque vous définissez un événement d’achèvement de tâche, toutes les tâches sont créés à partir que les événements seront termine immédiatement et ses continuations, le cas échéant, sont planifiées. Tâches des objets d’achèvement qui ont un `_ResultType` autre que `void` passe la valeur de leurs continuations.  
  
##  <a name="set_exception"></a>set_exception 

 Propage une exception à toutes les tâches associées à cet événement.  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>Paramètres  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="ctor"></a>task_completion_event 

 Construit un objet `task_completion_event`.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
