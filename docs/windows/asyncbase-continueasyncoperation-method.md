---
title: "AsyncBase::ContinueAsyncOperation, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ContinueAsyncOperation (méthode)"
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::ContinueAsyncOperation, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine si l'opération asynchrone doit continuer ou doit s'arrêter.  
  
## Syntaxe  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## Valeur de retour  
 `true` si l'état actuel de l'opération asynchrone est *started*,ce qui signifie que l'opération doit continuer.  Sinon, `false`, ce qui signifie que l'opération doit s'arrêter.  
  
## Configuration requise  
 **En\-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)