---
title: scheduler_resource_allocation_error, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_resource_allocation_error
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 52233a99e1d1a715fc7d52599ffeff18a3c2c34b
ms.lasthandoff: 02/24/2017

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
|[scheduler_resource_allocation_error, constructeur](#ctor)|Surchargé. Construit un objet `scheduler_resource_allocation_error`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_error_code (méthode)](#get_error_code)|Retourne le code d’erreur qui a provoqué l’exception.|  
  
## <a name="remarks"></a>Remarques  
 Cette exception est généralement levée lorsqu’un appel vers le système d’exploitation dans le Runtime d’accès concurrentiel échoue. Le code d’erreur qui devrait normalement être retourné à partir d’un appel à la méthode Win32 `GetLastError` est convertie en une valeur de type `HRESULT` et peut être récupéré à l’aide de la `get_error_code` méthode.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namegeterrorcodea-geterrorcode"></a><a name="get_error_code"></a>get_error_code 

 Retourne le code d’erreur qui a provoqué l’exception.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `HRESULT` la valeur de l’erreur qui a provoqué l’exception.  
  
##  <a name="a-namectora-schedulerresourceallocationerror"></a><a name="ctor"></a>scheduler_resource_allocation_error 

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

