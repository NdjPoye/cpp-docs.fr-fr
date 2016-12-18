---
title: "HStringReference::Operator==, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=="
dev_langs: 
  - "C++"
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator==, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si les deux paramètres sont égaux.  
  
## Syntaxe  
  
```cpp  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### Paramètres  
 `lhs`  
 Le premier paramètre à comparer.  `lhs` peut être un objet HStringReference, ou un handle HSTRING.  
  
 `rhs`  
 Le deuxième paramètre à comparer.`rhs` peut être un objet HStringReference ou un gestionnaire HSTRING.  
  
## Valeur de retour  
 `true` si les paramètres `lhs` et `rhs` sont égaux ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)