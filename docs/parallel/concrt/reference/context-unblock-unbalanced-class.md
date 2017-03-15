---
title: context_unblock_unbalanced, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
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
ms.openlocfilehash: 7341ff5d10b7f7752c49f18ea9b810824e347b1c
ms.lasthandoff: 02/24/2017

---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced, classe
Cette classe décrit une exception levée quand des appels aux méthodes `Block` et `Unblock` d'un objet `Context` ne sont pas correctement associés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[context_unblock_unbalanced, constructeur](#ctor)|Surchargé. Construit un objet `context_unblock_unbalanced`.|  
  
## <a name="remarks"></a>Remarques  
 Les appels à la `Block` et `Unblock` méthodes d’un `Context` objet doit toujours être associé correctement. Le Runtime d’accès concurrentiel permet les opérations de se produire dans n’importe quel ordre. Par exemple, un appel à `Block` peut être suivie par un appel à `Unblock`, ou vice versa. Cette exception serait levée si, par exemple, deux appels à la `Unblock` méthode ont été effectuées dans une ligne, sur un `Context` objet qui n’a pas été bloqué.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namectora-contextunblockunbalanced"></a><a name="ctor"></a>context_unblock_unbalanced 

 Construit un objet `context_unblock_unbalanced`.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

