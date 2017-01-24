---
title: "improper_lock, classe | Microsoft Docs"
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
  - "concrt/concurrency::improper_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_lock (classe)"
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# improper_lock, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'un verrou est interrompu incorrectement.  
  
## Syntaxe  
  
```  
class improper_lock : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[improper\_lock::improper\_lock, constructeur](../Topic/improper_lock::improper_lock%20Constructor.md)|Surchargé.  Construit une `improper_lock exception`.|  
  
## Notes  
 En général, cette exception est levée lorsqu'une tentative est faite pour acquérir de manière récursive un verrou non réentrant sur le même contexte.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `improper_lock`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section, classe](../../../parallel/concrt/reference/critical-section-class.md)   
 [reader\_writer\_lock, classe](../../../parallel/concrt/reference/reader-writer-lock-class.md)