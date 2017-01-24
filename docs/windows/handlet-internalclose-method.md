---
title: "HandleT::InternalClose, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InternalClose (méthode)"
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::InternalClose, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ferme l'objet HandleT en cours.  
  
## Syntaxe  
  
```  
virtual bool InternalClose();  
```  
  
## Valeur de retour  
 `true` si le HandleT actuel se ferme avec succès; sinon, `false`.  
  
## Remarques  
 InternalClose\(\) est protégé.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)