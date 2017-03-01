---
title: "Énumérations d’espace de noms d’accès concurrentiel (AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9555023e01cb765ca943fcaaf785cdc2b4e2d0d
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums-amp"></a>Énumérations d’espace de noms d’accès concurrentiel (AMP)
|||  
|-|-|  
|[access_type, énumération](#access_type)|[Énumération queuing_mode](#queuing_mode)|  
  
##  <a name="a-nameaccesstypea--accesstype-enumeration"></a><a name="access_type"></a>access_type, énumération  
 Type d’énumération utilisé pour représenter les différents types d’accès aux données.  
  
```  
enum access_type;  
```  
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`access_type_auto`|Choisir automatiquement le meilleur `access_type` pour l’accélérateur.|  
|`access_type_none`|Dédié. L’allocation est uniquement accessible sur l’accélérateur et non sur le processeur.|  
|`access_type_read`|Partagé. L’allocation est accessible sur l’accélérateur et lisible sur le processeur.|  
|`access_type_read_write`|Partagé. L’allocation est accessible sur l’accélérateur et est accessible en écriture sur le processeur.|  
|`access_type_write`|Partagé. L’allocation est accessible sur l’accélérateur et est accessible en lecture et en écriture sur le processeur.|  

  
##  <a name="a-namequeuingmodea--queuingmode-enumeration"></a><a name="queuing_mode"></a>Énumération queuing_mode  
 Spécifie les modes de files d’attente qui sont pris en charge sur l’accélérateur.  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>Valeurs  
  
|Nom|Description|  
|----------|-----------------|  
|`queuing_mode_immediate`|Un mode de files d’attente qui spécifie tous les commandes, par exemple, [parallel_for_each (fonction) (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), sont envoyées au périphérique accélérateur correspondant dès qu’elles sont retournées à l’appelant.|  
|`queuing_mode_automatic`|Un mode de files d’attente qui spécifie que commandes mises en attente une file d’attente de commande correspond à la [accelerator_view](accelerator-view-class.md) objet. Les commandes sont envoyées à l’appareil lors de la [accelerator_view::flush](accelerator-view-class.md#flush) est appelée.|   
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

