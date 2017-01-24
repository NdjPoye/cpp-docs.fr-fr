---
title: "InvokeHelper::InvokeHelper, constructeur | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InvokeHelper, constructeur"
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InvokeHelper::InvokeHelper, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
explicit InvokeHelper(  
   TCallback callback  
);  
```  
  
#### Paramètres  
 `callback`  
 Gestionnaire d'événements.  
  
## Remarques  
 Initialise une nouvelle instance de la classe InvokeHelper.  
  
 Le paramètre de modèle `TCallback` spécifie le type du gestionnaire d'événements.  
  
## Configuration requise  
 **En\-tête:** event.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [InvokeHelper, structure](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)