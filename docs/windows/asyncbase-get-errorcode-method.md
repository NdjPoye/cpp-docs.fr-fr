---
title: "AsyncBase::get_ErrorCode, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_ErrorCode (méthode)"
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::get_ErrorCode, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère le code d'erreur pour l'opération asynchrone en cours.  
  
## Syntaxe  
  
```  
STDMETHOD(  
   get_ErrorCode  
)(HRESULT* errorCode) override;  
```  
  
#### Paramètres  
 `errorCode`  
 L'emplacement où le code d'erreur actuel est enregistré.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_ILLEGAL\_METHOD\_CALL si l'opération asynchrone en cours est annulée.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)