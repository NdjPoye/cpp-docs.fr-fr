---
title: "AsyncBase::Close, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close (méthode)"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::Close, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ferme l'opération asynchrone.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## Valeur de retour  
 S\_OK si l'opération se ferme ou est déjà fermée; sinon, E\_ILLEGAL\_STATE\_CHANGE.  
  
## Remarques  
 Close\(\) est une implémentation par défaut d'IAsyncInfo::Close, et n'effectue pas de travail réel.  Pour réellement fermer une opération asynchrone, redéfinissez la méthode purement virtuelle OnClose\(\).  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)