---
title: static_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
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
ms.openlocfilehash: f36b1e1dcc68d94bdebd8b7b10f4fec735ce9fb5
ms.lasthandoff: 02/24/2017

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
|[static_partitioner, constructeur](#ctor)|Construit un objet `static_partitioner`.|  
|[~ static_partitioner, destructeur](#dtor)|Détruit un objet `static_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `static_partitioner`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-staticpartitioner"></a><a name="dtor"></a>~ static_partitioner 

 Détruit un objet `static_partitioner`.  
  
```
~static_partitioner();
```  
  
##  <a name="a-namectora-staticpartitioner"></a><a name="ctor"></a>static_partitioner 

 Construit un objet `static_partitioner`.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

