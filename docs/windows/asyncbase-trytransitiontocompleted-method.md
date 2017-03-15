---
title: "AsyncBase::TryTransitionToCompleted, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToCompleted (méthode)"
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::TryTransitionToCompleted, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si l'opération asynchrone en cours est terminée.  
  
## Syntaxe  
  
```  
bool TryTransitionToCompleted(  
   void  
);  
```  
  
## Valeur de retour  
 `true` si l'opération asynchrone est terminée; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)