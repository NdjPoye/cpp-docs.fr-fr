---
title: "HandleT::Close, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close (méthode)"
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT::Close, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ferme l'objet HandleT en cours.  
  
## Syntaxe  
  
```  
void Close();  
```  
  
## Remarques  
 Le handle qui est à la base du HandleT actuel est fermé, et le HandleT est défini à l'état non valide.  
  
 Si le handle ne se ferme pas correctement, une exception est levée dans le thread appelant.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)