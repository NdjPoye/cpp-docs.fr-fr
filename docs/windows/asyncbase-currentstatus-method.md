---
title: "AsyncBase::CurrentStatus, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::CurrentStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CurrentStatus (méthode)"
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::CurrentStatus, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère l'état de l'opération asynchrone actuelle.  
  
## Syntaxe  
  
```  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
#### Paramètres  
 `status`  
 L'emplacement où cette opération enregistre l'état actuel.  
  
## Remarques  
 Cette opération est thread\-safe.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)   
 [AsyncStatusInternal, énumération](../windows/asyncstatusinternal-enumeration.md)