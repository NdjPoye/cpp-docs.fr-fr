---
title: task_canceled, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: dcf930c7efd1a7d7b015919b2009440045dd18fe
ms.lasthandoff: 02/24/2017

---
# <a name="taskcanceled-class"></a>task_canceled, classe
Cette classe décrit une exception levée par la couche de tâches PPL pour forcer l’annulation de la tâche actuelle. Il est également levée par le `get()` méthode [tâches](/visualstudio/extensibility/debugger/task-class-internal-members), pour une tâche annulée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[task_canceled, constructeur](#ctor)|Surchargé. Construit un objet `task_canceled`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namectora-taskcanceled"></a><a name="ctor"></a>task_canceled 

 Construit un objet `task_canceled`.  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

