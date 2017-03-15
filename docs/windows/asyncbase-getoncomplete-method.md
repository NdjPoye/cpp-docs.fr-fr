---
title: "AsyncBase::GetOnComplete, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::GetOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnComplete (méthode)"
ms.assetid: f06ae02d-9a88-41d2-b749-bdc1a7ff8748
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::GetOnComplete, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie l'adresse du gestionnaire d'événements de complétion actuel vers la variable spécifiée.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetOnComplete  
)(TComplete** completeHandler);  
```  
  
#### Paramètres  
 `completeHandler`  
 L'emplacement où est stockée l'adresse du gestionnaire d'événements de complétion actuel.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_ILLEGAL\_METHOD\_CALL.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)