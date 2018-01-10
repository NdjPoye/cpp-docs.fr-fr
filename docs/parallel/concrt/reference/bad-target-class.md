---
title: bad_target, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs: C++
helpviewer_keywords: bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37cba64767d492559a52e9bf84c132b5f5ba1b50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="badtarget-class"></a>bad_target, classe
Cette classe décrit une exception levée quand un bloc de messagerie reçoit un pointeur vers une cible qui n'est pas valide pour l'opération en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[bad_target](#ctor)|Surchargé. Construit un objet `bad_target`.|  
  
## <a name="remarks"></a>Notes  
 Cette exception est généralement levée pour des raisons comme une cible essayant de consommer un message qui est réservé pour une cible différente ou annulant une réservation qu’il ne contient pas.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>bad_target 

 Construit un objet `bad_target`.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md)



