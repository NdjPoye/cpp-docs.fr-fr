---
title: "is_standard_layout, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_standard_layout"
  - "std::tr1::is_standard_layout"
  - "is_standard_layout"
  - "std.is_standard_layout"
  - "std::is_standard_layout"
  - "type_traits/std::is_standard_layout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_standard_layout (classe) (TR1)"
  - "is_standard_layout"
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_standard_layout, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est une disposition standard.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_standard_layout;  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Ty`|Type à interroger|  
  
## Notes  
 Une instance de ce prédicat de type a la valeur true si le type `Ty` est une classe qui a une disposition standard d'objets membres en mémoire. Sinon, sa valeur est false.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)