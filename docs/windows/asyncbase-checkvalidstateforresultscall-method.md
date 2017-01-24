---
title: "AsyncBase::CheckValidStateForResultsCall, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForResultsCall (méthode)"
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::CheckValidStateForResultsCall, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si les résultats d'une opération asynchrone peuvent être collectés dans l'état asynchrone en cours.  
  
## Syntaxe  
  
```  
inline HRESULT CheckValidStateForResultsCall();  
```  
  
## Valeur de retour  
 S\_OK si les résultats peuvent être collectés; sinon, E\_ILLEGAL\_METHOD\_CALLE\_ILLEGAL\_METHOD\_CALL.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)