---
title: "AsyncBase::put_Id, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::put_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "put_Id (méthode)"
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::put_Id, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit le handle de l'opération asynchrone.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   put_Id  
)(const unsigned int id);  
```  
  
#### Paramètres  
 `id`  
 Un handle différent de zéro.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_INVALIDARG ou E\_ILLEGAL\_METHOD\_CALL.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)