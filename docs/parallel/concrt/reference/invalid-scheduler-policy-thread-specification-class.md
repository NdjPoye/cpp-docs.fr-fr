---
title: invalid_scheduler_policy_thread_specification, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 267f8fef7aa376105d7dfcaf4ac995a9fd272a7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
|[invalid_scheduler_policy_thread_specification] (non valide-planificateur-stratégie-valeur-class.md #ctor|Surchargé. Construit un objet `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
##  <a name="ctor"></a>invalid_scheduler_policy_thread_specification 

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
 [SchedulerPolicy, classe](schedulerpolicy-class.md)
