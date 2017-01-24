---
title: "AsyncResultType, &#233;num&#233;ration | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncResultType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncResultType (énumération)"
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncResultType, &#233;num&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie le type de résultat retourné par la méthode GetResults\(\).  
  
## Syntaxe  
  
```  
enum AsyncResultType;  
```  
  
## Membres  
  
### Valeurs  
  
|Name|Description|  
|----------|-----------------|  
|`MultipleResults`|Un ensemble de plusieurs résultats, présentés progressivement entre l'état Démarré et avant que Close\(\) est appelé.|  
|`SingleResult`|Un résultat unique, qui est présenté une fois que l'événement Complete se produit.|  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)