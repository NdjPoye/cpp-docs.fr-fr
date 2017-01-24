---
title: "HString::Operator&lt;, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator<"
dev_langs: 
  - "C++"
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator&lt;, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si le premier paramètre est inférieur au deuxième paramètre.  
  
## Syntaxe  
  
```cpp  
  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### Paramètres  
 `lhs`  
 Le premier paramètre à comparer.  `lhs` peut être une référence à un HString.  
  
 `rhs`  
 Le deuxième paramètre à comparer.  `rhs` peut être une référence à un HString.  
  
## Valeur de retour  
 `true` si le paramètre `lhs` est inférieur au paramètre `rhs`; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)