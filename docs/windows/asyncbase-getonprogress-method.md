---
title: "AsyncBase::GetOnProgress, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::GetOnProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnProgress (méthode)"
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::GetOnProgress, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Copie l'adresse du gestionnaire d'événements de progression actuel vers la variable spécifiée.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### Paramètres  
 `progressHandler`  
 L'emplacement où est stockée l'adresse du gestionnaire d'événements de progression actuelle.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_ILLEGAL\_METHOD\_CALL.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)