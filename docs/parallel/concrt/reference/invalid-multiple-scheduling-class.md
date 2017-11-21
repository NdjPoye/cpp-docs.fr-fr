---
title: invalid_multiple_scheduling, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
dev_langs: C++
helpviewer_keywords: invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86d2680234b1d6f957e9f19f9cacc372f7fc8eff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling, classe
Cette classe décrit une exception levée quand un objet `task_handle` est planifié à plusieurs reprises à l'aide de la méthode `run` d'un objet `task_group` ou `structured_task_group` sans appel intermédiaire aux méthodes `wait` ou `run_and_wait`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class invalid_multiple_scheduling : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[invalid_multiple_scheduling](#ctor)|Surchargé. Construit un objet `invalid_multiple_scheduling`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>invalid_multiple_scheduling 

 Construit un objet `invalid_multiple_scheduling`.  
  
```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [task_handle, classe](task-handle-class.md)   
 [task_group, classe](task-group-class.md)   
 [exécuter](task-group-class.md)   
 [attente](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group, classe](structured-task-group-class.md)
