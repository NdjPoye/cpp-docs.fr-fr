---
title: "AsyncBase::FireProgress, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireProgress (méthode)"
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireProgress, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelle le gestionnaire d'événements de progression actuel.  
  
## Syntaxe  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### Paramètres  
 `arg`  
 La méthode du gestionnaire d'événements à appeler.  
  
## Remarques  
 `ProgressTraits` est dérivé de [ArgTraitsHelper, structure](../windows/argtraitshelper-structure.md).  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)