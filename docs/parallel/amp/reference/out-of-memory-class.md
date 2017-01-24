---
title: "out_of_memory, classe | Microsoft Docs"
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
  - "amprt/Concurrency::out_of_memory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out_of_memory (classe)"
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# out_of_memory, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'exception levée lorsqu'une méthode échoue à cause d'un échec de mémoire du système ou de périphérique.  
  
## Syntaxe  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[out\_of\_memory::out\_of\_memory, constructeur](../Topic/out_of_memory::out_of_memory%20Constructor.md)|Initialise une nouvelle instance de la classe `out_of_memory`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)