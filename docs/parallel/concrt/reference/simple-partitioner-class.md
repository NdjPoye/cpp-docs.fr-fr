---
title: simple_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
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
ms.openlocfilehash: dc90df5ba9fbbf5566a26a014a6a2db2ae4a0459
ms.lasthandoff: 02/24/2017

---
# <a name="simplepartitioner-class"></a>simple_partitioner, classe
La classe `simple_partitioner` représente un partitionnement statique de la plage itérée par `parallel_for`. Le partitionneur divise la plage en segments de sorte que chaque segment comporte au moins le nombre d'itérations spécifié par la taille du segment.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[simple_partitioner, constructeur](#ctor)|Construit un objet `simple_partitioner`.|  
|[~ simple_partitioner, destructeur](#dtor)|Détruit un objet `simple_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `simple_partitioner`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-simplepartitioner"></a><a name="dtor"></a>~ simple_partitioner 

 Détruit un objet `simple_partitioner`.  
  
```
~simple_partitioner();
```  
  
##  <a name="a-namectora-simplepartitioner"></a><a name="ctor"></a>simple_partitioner 

 Construit un objet `simple_partitioner`.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Chunk_size`  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

