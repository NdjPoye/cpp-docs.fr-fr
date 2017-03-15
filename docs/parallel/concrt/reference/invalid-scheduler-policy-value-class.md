---
title: invalid_scheduler_policy_value, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
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
ms.openlocfilehash: ff5b07b62923a289da1b47de08b527da212e4a2d
ms.lasthandoff: 02/24/2017

---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value, classe
Cette classe décrit une exception levée quand une clé de stratégie d'un objet `SchedulerPolicy` est défini sur une valeur non valide pour cette clé.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[invalid_scheduler_policy_value constructeur] (invalid-scheduler-policy-thread-specification-class.md#ctor|Surchargé. Construit un objet `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
    
##  <a name="a-namectora-invalidschedulerpolicyvalue"></a><a name="ctor"></a>invalid_scheduler_policy_value 

 Construit un objet `invalid_scheduler_policy_value`.  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  

## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [SchedulerPolicy (classe)](schedulerpolicy-class.md)

