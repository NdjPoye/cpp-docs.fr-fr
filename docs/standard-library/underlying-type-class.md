---
title: "underlying_type (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "underlying_type"
  - "std.underlying_type"
  - "std::underlying_type"
  - "type_traits/std::underlying_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underlying_type"
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# underlying_type (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère le type intégral sous\-jacent pour un type d’énumération.  
  
## Syntaxe  
  
```  
template <class T>  
    struct underlying_type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Le `type` typedef de membre de la classe de modèle désigne le type intégral sous\-jacent de `T`, lorsque `T` est un type énumération, sinon il n’existe aucun typedef de membre `type`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)