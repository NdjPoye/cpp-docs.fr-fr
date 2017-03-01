---
title: invalid_scheduler_policy_thread_specification, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: c09719412e38a4f056eabc39a66a684caa0659d4
ms.lasthandoff: 02/24/2017

---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification, classe
Cette classe décrit une exception levée quand est effectuée une tentative de définir les limites d'accès concurrentiel d'un objet `SchedulerPolicy` de telle sorte que la valeur de la clé `MinConcurrency` est inférieure à celle de la clé `MaxConcurrency`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification constructeur] (non valide-scheduler-stratégie-valeur-class.md #ctor|Surchargé. Construit un objet `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
##  <a name="a-namectora-invalidschedulerpolicythreadspecification"></a><a name="ctor"></a>invalid_scheduler_policy_thread_specification 

 Construit un objet `invalid_scheduler_policy_value`.  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  

## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [SchedulerPolicy (classe)](schedulerpolicy-class.md)

