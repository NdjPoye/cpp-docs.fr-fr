---
title: "AsyncBase::OnCancel, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::OnCancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnCancel (méthode)"
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::OnCancel, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En cas de substitution dans une classe dérivée, annule une opération asynchrone.  
  
## Syntaxe  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel, méthode](../windows/asyncbase-cancel-method.md)