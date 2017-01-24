---
title: "&#201;num&#233;ration queuing_mode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::queuing_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queuing_mode (énumération)"
ms.assetid: 8c641054-906d-40b3-bbb4-f62af9356a14
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;num&#233;ration queuing_mode
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Spécifie les modes de mise en file d'attente pris en charge sur l'accélérateur.  
  
## Syntaxe  
  
```  
enum queuing_mode;  
```  
  
## Membres  
  
### Valeurs  
  
|Nom|Description|  
|---------|-----------------|  
|`queuing_mode_immediate`|Un mode de mise en file d'attente qui spécifie que toutes les commandes, par exemple, [parallel\_for\_each, fonction \(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md), sont envoyées à le périphérique accélérateur correspondant dès qu'elles reviendront à l'appelant.|  
|`queuing_mode_automatic`|Un mode de mise en file d'attente qui spécifie que les commandes mises en file d'attente sur une file d'attente de commande qui correspond à l'objet [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md).  Les commandes sont envoyées au périphérique lorsque [accelerator\_view::flush](../Topic/accelerator_view::flush%20Method.md) est appelé.|  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)