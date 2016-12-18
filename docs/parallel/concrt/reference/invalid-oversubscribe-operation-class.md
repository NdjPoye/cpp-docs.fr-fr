---
title: "invalid_oversubscribe_operation, classe | Microsoft Docs"
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
  - "concrt/concurrency::invalid_oversubscribe_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_oversubscribe_operation (classe)"
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
caps.latest.revision: 19
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_oversubscribe_operation, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `Context::Oversubscribe` est appelée avec le paramètre d' `_BeginOversubscription` à `false` sans appel précédent à la méthode d' `Context::Oversubscribe` avec le jeu de paramètres d' `_BeginOversubscription` à `true`.  
  
## Syntaxe  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_oversubscribe\_operation::invalid\_oversubscribe\_operation, constructeur](../Topic/invalid_oversubscribe_operation::invalid_oversubscribe_operation%20Constructor.md)|Surchargé.  Construit un objet `invalid_oversubscribe_operation`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Context::Oversubscribe, méthode](../Topic/Context::Oversubscribe%20Method.md)