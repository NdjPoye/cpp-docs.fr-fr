---
title: "AsyncBase::CheckValidStateForDelegateCall, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForDelegateCall (méthode)"
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::CheckValidStateForDelegateCall, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si les propriétés de délégués peuvent être modifiées dans l'état asynchrone en cours.  
  
## Syntaxe  
  
```  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## Valeur de retour  
 S\_OK si les propriétés de délégués peuvent être modifiées; sinon, E\_ILLEGAL\_METHOD\_CALL.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)