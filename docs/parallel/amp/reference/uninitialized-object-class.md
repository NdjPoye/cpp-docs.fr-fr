---
title: "uninitialized_object, classe | Microsoft Docs"
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
  - "amprt/Concurrency::uninitialized_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uninitialized_object (classe)"
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uninitialized_object, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'exception levée quand un objet non\-initialisé est utilisé.  
  
## Syntaxe  
  
```  
class uninitialized_object : public runtime_exception;  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[uninitialized\_object::uninitialized\_object, constructeur](../Topic/uninitialized_object::uninitialized_object%20Constructor.md)|Initialise une nouvelle instance de la classe `uninitialized_object`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)