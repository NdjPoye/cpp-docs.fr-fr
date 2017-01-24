---
title: "InvokeHelper::callback_, donn&#233;e de membre | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::InvokeHelper::callback_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "callback_ (membre de données)"
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InvokeHelper::callback_, donn&#233;e de membre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
TCallback callback_;  
```  
  
## Remarques  
 Représente le gestionnaire d'événements à appeler lorsqu'un événement se produit.  
  
 Le paramètre de modèle `TCallback` spécifie le type du gestionnaire d'événements.  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [InvokeHelper, structure](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)