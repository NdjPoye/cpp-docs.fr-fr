---
title: affinity_partitioner, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
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
ms.openlocfilehash: 92da56fd5b84537c2fa01a252dfee202c729cc96
ms.lasthandoff: 02/24/2017

---
# <a name="affinitypartitioner-class"></a>affinity_partitioner, classe
La classe `affinity_partitioner` est similaire à la classe `static_partitioner`, mais elle améliore l'affinité du cache par son choix de mapper les sous-plages aux threads de travail. Elle peut améliorer considérablement les performances quand une boucle est réexécutée sur le même jeu de données et que les données tiennent dans le cache. Notez que le même objet `affinity_partitioner` doit être utilisé avec les itérations suivantes d'une boucle parallèle exécutée sur un jeu de données particulier, pour bénéficier de la localité des données.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[affinity_partitioner, constructeur](#ctor)|Construit un objet `affinity_partitioner`.|  
|[~ affinity_partitioner, destructeur](#dtor)|Détruit une `affinity_partitioner` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppl.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-affinitypartitioner"></a><a name="dtor"></a>~ affinity_partitioner 

 Détruit une `affinity_partitioner` objet.  
  
```
~affinity_partitioner();
```  
  
##  <a name="a-namectora-affinitypartitioner"></a><a name="ctor"></a>affinity_partitioner 

 Construit un objet `affinity_partitioner`.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

