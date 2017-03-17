---
title: invalid_compute_domain, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs:
- C++
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
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
ms.openlocfilehash: e37012f62a40649876d043c3a0e89a1655c40455
ms.lasthandoff: 02/24/2017

---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain, classe
L’exception qui est levée lorsque le runtime ne peut pas démarrer un noyau à l’aide du domaine de calcul spécifié à la [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) site d’appel.  

  
## <a name="syntax"></a>Syntaxe  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[invalid_compute_domain, constructeur](#ctor)|Initialise une nouvelle instance de la classe `invalid_compute_domain`.|  

  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  

## <a name="ctor"></a>invalid_compute_domain 

Initialise une nouvelle instance de la classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Description de l'erreur.  
  
### <a name="return-value"></a>Valeur de retour  
 Une instance de la `invalid_compute_domain` (classe)  
    
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

