---
title: "AsyncBase::Cancel, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Cancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cancel (méthode)"
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Cancel, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Annule une opération asynchrone.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## Valeur de retour  
 Par défaut, retourne toujours S\_OK.  
  
## Remarques  
 Cancel\(\) est une implémentation par défaut d'IAsyncInfo::Cancel, et n'effectue pas de travail réel.  Pour réellement annuler une opération asynchrone, redéfinissez la méthode purement virtuelle OnCancel\(\).  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)