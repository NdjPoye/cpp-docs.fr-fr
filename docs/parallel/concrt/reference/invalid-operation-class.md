---
title: "invalid_operation, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_operation (classe)"
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_operation, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque l'effectue une opération non valide qui plus précisément n'est pas décrite par un autre type d'exception levée par le runtime d'accès concurrentiel.  
  
## Syntaxe  
  
```  
class invalid_operation : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_operation::invalid\_operation, constructeur](../Topic/invalid_operation::invalid_operation%20Constructor.md)|Surchargé.  Construit un objet `invalid_operation`.|  
  
## Notes  
 Les différentes méthodes qui lèvent cette exception indiqueront généralement dans quelles circonstances elles les lèveront.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_operation`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)