---
title: "&lt;atomic&gt;, énumérations | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic/std::memory_order
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 
helpviewer_keywords:
- std::memory_order
manager: ghogen
ms.openlocfilehash: 5f5c286375699d233d1bc9dadd3f44992309fa0a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltatomicgt-enums"></a>&lt;atomic&gt;, énumérations
  
##  <a name="memory_order_enum"></a>  memory_order, énumération  
 Fournit les noms symboliques des opérations de synchronisation sur les emplacements de mémoire. Ces opérations affectent l’affichage des assignations d’un thread dans un autre thread.  
  
```
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```  
  
### <a name="remarks"></a>Notes  
  
|||  
|-|-|  
|`memory_order_relaxed`|Aucun ordre nécessaire.|  
|`memory_order_consume`|Une opération de chargement agit comme une opération de consommation sur l’emplacement de mémoire.|  
|`memory_order_acquire`|Une opération de chargement agit comme une opération d’acquisition sur l’emplacement de mémoire.|  
|`memory_order_release`|Une opération de stockage agit comme une opération de libération sur l’emplacement de mémoire.|  
|`memory_order_acq_rel`|Combine `memory_order_acquire` et `memory_order_release`.|  
|`memory_order_seq_cst`|Combine `memory_order_acquire` et `memory_order_release`. Les accès à la mémoire marqués comme `memory_order_seq_cst` doivent être cohérents de façon séquentielle.|  
  
## <a name="see-also"></a>Voir aussi  
 [\<atomic>](../standard-library/atomic.md)



