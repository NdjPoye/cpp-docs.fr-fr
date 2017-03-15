---
title: auto_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
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
ms.openlocfilehash: 8092a0d6c4fe6053a3bb7e80e659ab6a7628664a
ms.lasthandoff: 02/24/2017

---
# <a name="autopartitioner-class"></a>auto_partitioner, classe
La classe `auto_partitioner` représente la méthode par défaut que `parallel_for`, `parallel_for_each` et `parallel_transform` utilisent pour partitionner la plage au sein de laquelle ils itèrent. Cette méthode de partitionnement utilise un vol de plage pour équilibrer la charge et annuler par itération.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class auto_partitioner;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[auto_partitioner, constructeur](#ctor)|Construit un objet `auto_partitioner`.|  
|[~ auto_partitioner, destructeur](#dtor)|Détruit un objet `auto_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `auto_partitioner`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-autopartitioner"></a><a name="dtor"></a>~ auto_partitioner 

 Détruit un objet `auto_partitioner`.  
  
```
~auto_partitioner();
```  
  
##  <a name="a-namectora-autopartitioner"></a><a name="ctor"></a>auto_partitioner 

 Construit un objet `auto_partitioner`.  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

