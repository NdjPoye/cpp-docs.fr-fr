---
title: "HANDLETraits::Close, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close (méthode)"
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HANDLETraits::Close, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ferme le handle spécifié.  
  
## Syntaxe  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### Paramètres  
 `h`  
 Le handle à fermer.  
  
## Valeur de retour  
 **true** si le handle `h` s'est fermé avec succès; sinon, **false**.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers::HandleTraits  
  
## Voir aussi  
 [HANDLETraits, structure](../windows/handletraits-structure.md)