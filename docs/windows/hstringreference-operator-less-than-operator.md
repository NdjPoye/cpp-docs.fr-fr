---
title: "HStringReference::Operator&lt;, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<"
dev_langs: 
  - "C++"
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator&lt;, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si le premier paramètre est inférieur au deuxième paramètre.  
  
## Syntaxe  
  
```cpp  
  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
  
```  
  
#### Paramètres  
 `lhs`  
 Le premier paramètre à comparer.  `lhs` peut être une référence à un HStringReference.  
  
 `rhs`  
 Le deuxième paramètre à comparer.  `rhs` peut être une référence à un HStringReference.  
  
## Valeur de retour  
 `true` si le paramètre `lhs` est inférieur au paramètre `rhs` ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)