---
title: task_handle, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
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
ms.openlocfilehash: 0fef1ef7b1c02287a0113eb80be413e4a17dc1a4
ms.lasthandoff: 03/17/2017

---
# <a name="taskhandle-class"></a>task_handle, classe
La classe `task_handle` représente un élément de travail parallèle individuel. Elle encapsule les instructions et les données requises pour exécuter un élément de travail.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Function`  
 Le type de l’objet de fonction qui sera appelée pour exécuter le travail représenté par la `task_handle` objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[task_handle](#ctor)|Construit un nouveau `task_handle` objet. Le travail de la tâche est effectué en appelant la fonction spécifiée en tant que paramètre au constructeur.|  
|[~ task_handle, destructeur](#dtor)|Détruit le `task_handle` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator()](#task_handle__operator_call)|L’opérateur d’appel de fonction appelé par le runtime pour effectuer le travail du handle de tâche.|  
  
## <a name="remarks"></a>Remarques  
 `task_handle`objets peuvent être utilisés conjointement avec un `structured_task_group` ou plus général `task_group` objet, pour décomposer le travail en tâches parallèles. Pour plus d’informations, consultez [le parallélisme des tâches](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Notez que le créateur d’une `task_handle` objet est responsable de la durée de vie du `task_handle` objet jusqu'à ce qu’il n’est plus requis par le Runtime d’accès concurrentiel. En règle générale, cela signifie que la `task_handle` objet ne doit pas être détruit tant que le `wait` ou `run_and_wait` procédé de la `task_group` ou `structured_task_group` à laquelle elle est mise en attente a été appelée.  
  
 `task_handle`les objets sont généralement utilisés conjointement à des expressions lambda C++. Étant donné que vous ne connaissez pas le type réel de l’expression lambda, le [make_task](concurrency-namespace-functions.md#make_task) fonction est généralement utilisée pour créer un `task_handle` objet.  
  
 Le runtime crée une copie de la fonction de travail que vous passez à un `task_handle` objet. Par conséquent, toute modification d’état qui se produire dans une fonction de l’objet que vous passez à un `task_handle` objet n’apparaît pas dans votre copie de cet objet de fonction.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `task_handle`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="task_handle__operator_call"></a>operator() 

 L’opérateur d’appel de fonction appelé par le runtime pour effectuer le travail du handle de tâche.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a>task_handle 

 Construit un nouveau `task_handle` objet. Le travail de la tâche est effectué en appelant la fonction spécifiée en tant que paramètre au constructeur.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Func`  
 La fonction qui sera appelée pour exécuter le travail représenté par la `task_handle` objet. Il peut s’agir d’un functor de lambda, un pointeur vers une fonction, ou de tout objet qui prend en charge une version de l’opérateur d’appel de fonction avec la signature `void operator()()`.  
  
### <a name="remarks"></a>Remarques  
 Le runtime crée une copie de la fonction de travail que vous passez au constructeur. Par conséquent, toute modification d’état qui se produire dans une fonction de l’objet que vous passez à un `task_handle` objet n’apparaît pas dans votre copie de cet objet de fonction.  
  
##  <a name="dtor"></a>~ task_handle 

 Détruit le `task_handle` objet.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [task_group, classe](task-group-class.md)   
 [structured_task_group, classe](structured-task-group-class.md)

