---
title: "AsyncBase::get_Id, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_Id (méthode)"
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_Id, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère le handle de l'opération asynchrone.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### Paramètres  
 `id`  
 Emplacement où le handle sera enregistré.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_ILLEGAL\_METHOD\_CALL.  
  
## Remarques  
 Cette méthode implémente IAsyncInfo::get\_Id.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)