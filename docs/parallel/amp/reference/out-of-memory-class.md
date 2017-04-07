---
title: out_of_memory, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs:
- C++
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
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
ms.openlocfilehash: b593f8f85d4e36496f2ec2fc7bbadf8f2bfd742e
ms.lasthandoff: 02/24/2017

---
# <a name="outofmemory-class"></a>out_of_memory, classe
Exception levée lorsqu’une méthode échoue en raison d’un manque de mémoire système ou périphérique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[out_of_memory, constructeur](#ctor)|Initialise une nouvelle instance de la classe `out_of_memory`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  
## <a name="ctor"></a>out_of_memory 

 Initialise une nouvelle instance de la classe.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
explicit out_of_memory(  
    const char * _Message ) throw();  
  
out_of_memory () throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Description de l'erreur.  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvelle instance de la classe `out_of_memory`.  
  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

