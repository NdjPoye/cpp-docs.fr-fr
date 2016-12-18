---
title: "invalid_compute_domain, classe | Microsoft Docs"
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
  - "amprt/Concurrency::invalid_compute_domain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_compute_domain (classe)"
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_compute_domain, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Exception levée lorsque le runtime ne peut pas démarrer cœur à l'aide du champ de calcul spécifié au site d'appel de [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) .  
  
## Syntaxe  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[invalid\_compute\_domain::invalid\_compute\_domain, constructeur](../Topic/invalid_compute_domain::invalid_compute_domain%20Constructor.md)|Initialise une nouvelle instance de la classe `invalid_compute_domain`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)