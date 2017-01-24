---
title: "is_nothrow_move_constructible, classe | Microsoft Docs"
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
  - "is_nothrow_move_constructible"
  - "std.is_nothrow_move_constructible"
  - "std::is_nothrow_move_constructible"
  - "type_traits/std::is_nothrow_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_move_constructible"
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_nothrow_move_constructible, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un constructeur de déplacement [nothrow](../cpp/nothrow-cpp.md).  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_nothrow_move_constructible;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` a un constructeur de déplacement nothrow. Sinon, sa valeur est false.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)