---
title: scheduler_resource_allocation_error, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 84f32bb6192057c9d5872147cc8ef0bd2c13b349
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error, classe
Cette classe décrit une exception levée en raison d'un échec d'acquisition d'une ressource critique dans le runtime d'accès concurrentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_resource_allocation_error](#ctor)|Surchargé. Construit un objet `scheduler_resource_allocation_error`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_error_code](#get_error_code)|Retourne le code d’erreur qui a provoqué l’exception.|  
  
## <a name="remarks"></a>Notes  
 Cette exception est généralement levée lorsqu’un appel vers le système d’exploitation dans le Runtime d’accès concurrentiel échoue. Le code d’erreur qui devrait normalement être retourné à partir d’un appel à la méthode Win32 `GetLastError` est convertie en une valeur de type `HRESULT` et peut être récupéré à l’aide de la `get_error_code` méthode.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="get_error_code"></a>get_error_code 

 Retourne le code d’erreur qui a provoqué l’exception.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `HRESULT` la valeur de l’erreur qui a provoqué l’exception.  
  
##  <a name="ctor"></a>scheduler_resource_allocation_error 

 Construit un objet `scheduler_resource_allocation_error`.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
 `_Hresult`  
 Le `HRESULT` la valeur de l’erreur qui a provoqué l’exception.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

