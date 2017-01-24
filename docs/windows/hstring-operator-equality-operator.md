---
title: "HString::Operator==, op&#233;rateur | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator=="
dev_langs: 
  - "C++"
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator==, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si les deux paramètres sont égaux.  
  
## Syntaxe  
  
```cpp  
  
inline bool operator==(  
               const HString& lhs,   
               const HString& rhs) throw()  
  
inline bool operator==(  
                const HString& lhs,   
                const HStringReference& rhs) throw()  
  
inline bool operator==(  
                const HStringReference& lhs,   
                const HString& rhs) throw()  
  
inline bool operator==(  
                 const HSTRING& lhs,   
                 const HString& rhs) throw()  
  
inline bool operator==(  
                 const HString& lhs,   
                 const HSTRING& rhs) throw()  
  
```  
  
#### Paramètres  
 `lhs`  
 Le premier paramètre à comparer.  `lhs` peut être un objet HString ou un objet HStringReference, ou encore un handle HSTRING.  
  
 `rhs`  
 Le deuxième paramètre à comparer.`rhs` peut être un objet HString ou un objet HStringReference, ou encore un handle HSTRING.  
  
## Valeur de retour  
 `true` si les paramètres `lhs` et `rhs` sont égaux ; sinon, `false`.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)