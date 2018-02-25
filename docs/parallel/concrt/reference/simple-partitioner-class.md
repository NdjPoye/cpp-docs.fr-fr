---
title: simple_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4b4b92e3ad6324b3f25862c81892fde8f2c1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
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
|[simple_partitioner](#ctor)|Construit un objet `simple_partitioner`.|  
|[~ simple_partitioner, destructeur](#dtor)|Détruit un objet `simple_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `simple_partitioner`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="dtor"></a> ~simple_partitioner 

 Détruit un objet `simple_partitioner`.  
  
```
~simple_partitioner();
```  
  
##  <a name="ctor"></a> simple_partitioner 

 Construit un objet `simple_partitioner`.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Chunk_size`  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
