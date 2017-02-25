---
title: "runtime_exception, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d_abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_exception (classe)"
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# runtime_exception, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Le type de base des exceptions dans la bibliothèque C\+\+ Accelerated Massive Parallelism \(AMP\).  
  
## Syntaxe  
  
```  
class runtime_exception : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[runtime\_exception::runtime\_exception, constructeur](../Topic/runtime_exception::runtime_exception%20Constructor.md)|Initialise une nouvelle instance de la classe `runtime_exception`.|  
|[runtime\_exception::~runtime\_exception, destructeur](../Topic/runtime_exception::~runtime_exception%20Destructor.md)|Détruit l'objet `runtime_exception`.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[runtime\_exception::get\_error\_code, méthode](../Topic/runtime_exception::get_error_code%20Method.md)|Retourne le code d'erreur qui a provoqué l'exception.|  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[runtime\_exception::operator\=, opérateur](../Topic/runtime_exception::operator=%20Operator.md)|Copie le contenu de l'objet `runtime_exception` spécifié dans celui\-ci.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)