---
title: tile_barrier, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tile_barrier
dev_langs:
- C++
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: 17
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
ms.openlocfilehash: 7ace6bb366881f9e5a9678b3a005f3079542c9cd
ms.lasthandoff: 02/24/2017

---
# <a name="tilebarrier-class"></a>tile_barrier, classe
Synchronise l’exécution des threads qui s’exécutent dans le groupe de threads (la mosaïque) à l’aide de `wait` méthodes. Seulement le runtime peut instancier cette classe.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
class tile_barrier;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[tile_barrier, constructeur](#ctor)|Initialise une nouvelle instance de la classe `tile_barrier`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Wait (méthode)](#wait)|Fait en sorte que tous les threads dans le groupe de threads (mosaïque) pour arrêter l’exécution jusqu'à la fin de tous les threads dans la mosaïque en attente.|  
|[wait_with_all_memory_fence (méthode)](#wait_with_all_memory_fence)|Bloque l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire ont été effectuées et tous les threads dans la mosaïque ont atteint cet appel.|  
|[wait_with_global_memory_fence (méthode)](#wait_with_global_memory_fence)|Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les accès mémoire globale ont été effectuées et tous les threads dans la mosaïque ont atteint cet appel.|  
|[wait_with_tile_static_memory_fence (méthode)](#wait_with_tile_static_memory_fence)|Bloque l’exécution de tous les threads dans une mosaïque tant que tous les `tile_static` accès mémoire ont été effectuées et tous les threads dans la mosaïque ont atteint cet appel.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `tile_barrier`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  

## <a name="a-nametilebarrierctora--tilebarrier-constructor"></a><a name="tile_barrier__ctor"></a>tile_barrier, constructeur  
 Initialise une nouvelle instance de la classe en copiant une existante.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `tile_barrier` objet à copier.  

## <a name="a-namewaita--wait"></a><a name="wait"></a>attente 
Fait en sorte que tous les threads dans le groupe de threads (mosaïque) pour arrêter l’exécution jusqu'à la fin de tous les threads dans la mosaïque en attente.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
void wait() const restrict(amp);  
```    

## <a name="a-namewaitwithallmemoryfencea--waitwithallmemoryfence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les threads dans une mosaïque ont atteint cet appel. Cela garantit que tous les accès mémoire sont visibles à d’autres threads dans la vignette de thread et ont été exécutées dans l’ordre du programme.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="a-namewaitwithglobalmemoryfencea--waitwithglobalmemoryfence"></a><a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les threads dans une mosaïque ont atteint cet appel. Cela garantit que tous les accès mémoire globale sont visibles à d’autres threads dans la vignette de thread et ont été exécutées dans l’ordre du programme.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="a-namewaitwithtilestaticmemoryfencea--waitwithtilestaticmemoryfence"></a><a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Empêche l’exécution de tous les threads dans une mosaïque jusqu'à ce que tous les threads dans une mosaïque ont atteint cet appel. Cela garantit que `tile_static`mémoire accès sont visibles à d’autres threads dans la vignette de thread et ont été exécutées dans l’ordre du programme.  
  
### <a name="syntax"></a>Syntaxe 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

