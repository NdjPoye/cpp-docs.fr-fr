---
title: "HStringReference::Operator=, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator=, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déplace la valeur d'un autre objet HStringReference vers l'objet HStringReference actuel.  
  
## Syntaxe  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### Paramètres  
 `other`  
 Un objet HStringReference existant.  
  
## Remarques  
 La valeur de l'objet `other` existant est copiée vers l'objet HStringReference actuel, puis l'objet `other` est détruit.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)