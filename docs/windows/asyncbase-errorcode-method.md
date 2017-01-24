---
title: "AsyncBase::ErrorCode, m&#233;thode | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorCode (méthode)"
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::ErrorCode, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère le code d'erreur pour l'opération asynchrone en cours.  
  
## Syntaxe  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### Paramètres  
 `error`  
 L'emplacement où cette opération enregistre le code d'erreur actuel.  
  
## Remarques  
 Cette opération est thread\-safe.  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)