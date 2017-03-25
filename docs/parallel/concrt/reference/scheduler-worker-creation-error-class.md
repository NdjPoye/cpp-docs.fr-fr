---
title: scheduler_worker_creation_error, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: 9
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
ms.openlocfilehash: aee9d72447aca692fa25d675bdc5f727fa5b5c15
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error, classe
Cette classe décrit une exception levée en raison d'un échec de création d'un contexte d'exécution de travail dans le runtime d'accès concurrentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_worker_creation_error](#ctor)|Surchargé. Construit un objet `scheduler_worker_creation_error`.|  
  
## <a name="remarks"></a>Remarques  
 Cette exception est généralement levée lorsqu’un appel au système d’exploitation pour créer des contextes d’exécution dans le Runtime d’accès concurrentiel échoue. Contextes d’exécution sont des threads qui exécutent des tâches dans le Runtime d’accès concurrentiel. Le code d’erreur qui devrait normalement être retourné à partir d’un appel à la méthode Win32 `GetLastError` est convertie en une valeur de type `HRESULT` et peut être récupéré à l’aide de la méthode de classe de base `get_error_code`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>scheduler_worker_creation_error 

 Construit un objet `scheduler_worker_creation_error`.  
  
```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
 `_Hresult`  
 Le `HRESULT` la valeur de l’erreur qui a provoqué l’exception.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

