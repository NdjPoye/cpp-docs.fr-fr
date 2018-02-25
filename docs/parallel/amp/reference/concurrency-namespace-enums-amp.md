---
title: "Énumérations d’espace de noms d’accès concurrentiel (AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d17378a34698cc80d356983898e0023b76877140
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-enums-amp"></a>Énumérations d’espace de noms d’accès concurrentiel (AMP)
|||  
|-|-|  
|[access_type Enumeration](#access_type)|[queuing_mode Enumeration](#queuing_mode)|  
  
##  <a name="access_type"></a>  access_type Enumeration  
 Type d’énumération utilisé pour désigner les différents types d’accès aux données.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`access_type_auto`|Choisir automatiquement le meilleur `access_type` pour l’accélérateur.|  
|`access_type_none`|Dédié. L’allocation est uniquement accessible sur l’accélérateur et non sur l’UC.|  
|`access_type_read`|Partagé. L’allocation est accessible sur l’accélérateur et est accessible en lecture sur l’UC.|  
|`access_type_read_write`|Partagé. L’allocation est accessible sur l’accélérateur et est accessible en écriture sur l’UC.|  
|`access_type_write`|Partagé. L’allocation est accessible sur l’accélérateur et est accessible en lecture et en écriture sur le processeur.|  

  
##  <a name="queuing_mode"></a>  queuing_mode Enumeration  
 Spécifie les modes de files d’attente qui sont pris en charge sur l’accélérateur.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`queuing_mode_immediate`|Un mode de files d’attente qui spécifie tous les commandes, par exemple, [parallel_for_each, fonction (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), sont envoyés à l’appareil d’accélérateur correspondant dès qu’elles sont retournées à l’appelant.|  
|`queuing_mode_automatic`|Un mode de files d’attente qui spécifie que commandes mises en attente une file d’attente de la commande qui correspond à la [accelerator_view](accelerator-view-class.md) objet. Les commandes sont envoyées à l’appareil lors de la [accelerator_view::flush](accelerator-view-class.md#flush) est appelée.|   
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)
