---
title: "AsyncBase::Start, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start (méthode)"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::Start, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Démarre l'opération asynchrone.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## Valeur de retour  
 S\_OK si l'opération démarre ou est déjà démarrée; sinon, E\_ILLEGAL\_STATE\_CHANGE.  
  
## Remarques  
 Start\(\) est une implémentation par défaut d'IAsyncInfo::Start, et n'effectue pas de travail réel.  Pour réellement démarrer une opération asynchrone, redéfinissez la méthode purement virtuelle OnStart\(\).  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)