---
title: "CompareStringOrdinal, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal"
dev_langs: 
  - "C++"
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CompareStringOrdinal, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```cpp  
  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### Paramètres  
 `lhs`  
 Le première HSTRING à comparer.  
  
 `rhs`  
 Le deuxième HSTRING à comparer.  
  
## Valeur de retour  
  
|Valeur|Condition|  
|------------|---------------|  
|\-1|`lhs` est inférieur à `rhs`.|  
|0|`lhs` est égal à `rhs`.|  
|1|`lhs` est supérieur à `rhs`.|  
  
## Notes  
 Compare deux objets HSTRING spécifiés et retourne un entier indiquant leur position relative dans un ordre de tri.  
  
## Configuration requise  
 **En\-tête :** corewrappers.h  
  
 **Espace de noms :** Microsoft::WRL::Wrappers::Details  
  
## Voir aussi  
 [Microsoft::WRL::Wrappers::Details, espace de noms](../windows/microsoft-wrl-wrappers-details-namespace.md)