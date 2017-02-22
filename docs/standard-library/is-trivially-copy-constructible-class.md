---
title: "is_trivially_copy_constructible, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_trivially_copy_constructible"
  - "std.is_trivially_copy_constructible"
  - "std::is_trivially_copy_constructible"
  - "type_traits/std::is_trivially_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_constructible"
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# is_trivially_copy_constructible, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un constructeur de copie trivial.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_trivially_copy_constructible;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est une classe qui a un constructeur de copie trivial. Sinon, sa valeur est false.  
  
 Un constructeur de copie pour une classe `T` est triviale si elle est implicitement déclarée, la classe `T` n’a pas les fonctions virtuelles ou les bases virtuelles, toutes les bases directes de la classe `T` ont des constructeurs de copie trivial, les classes de tous les membres de données non statiques de type de classe possèdent des constructeurs de copie trivial, et les classes de tous les membres de données non statiques de type tableau de classe possèdent des constructeurs de copie trivial.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)