---
title: static_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20dad961b694042c721f388c9a40e0bf99b9b77d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="staticpartitioner-class"></a>static_partitioner, classe
La classe `static_partitioner` représente un partitionnement statique de la plage itérée par `parallel_for`. Le partitionneur divise la plage en autant de segments que de travaux disponibles pour le planificateur sous-jacent.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[static_partitioner](#ctor)|Construit un objet `static_partitioner`.|  
|[~ static_partitioner, destructeur](#dtor)|Détruit un objet `static_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `static_partitioner`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="dtor"></a> ~static_partitioner 

 Détruit un objet `static_partitioner`.  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a> static_partitioner 

 Construit un objet `static_partitioner`.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
