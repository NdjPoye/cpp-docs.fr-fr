---
title: "CancelTransitionPolicy, &#233;num&#233;ration | Microsoft Docs"
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
  - "module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CancelTransitionPolicy, énumération"
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CancelTransitionPolicy, &#233;num&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique comment la tentative de transition vers un état terminal de complétion ou d'erreur d'une opération asynchrone doit se comporter par rapport à un état annulé à la demande du client.  
  
## Syntaxe  
  
```  
enum CancelTransitionPolicy;  
```  
  
## Membres  
  
### Valeurs  
  
|Name|Description|  
|----------|-----------------|  
|`RemainCanceled`|Si l'opération asynchrone est actuellement à l'état annulé à la demande du client, cela indique qu'elle restera à l'état annulé par opposition à la transition vers un état final de complétion ou d'erreur.|  
|`TransitionFromCanceled`|Si l'opération asynchrone est actuellement à l'état annulé à la demande du client, cela indique que l'état doit passer de l'état annulé à l'état final de complétion ou d'erreur, déterminé par l'appel qui utilise cette balise.|  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)