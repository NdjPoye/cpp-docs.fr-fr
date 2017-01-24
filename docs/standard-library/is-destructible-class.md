---
title: "is_destructible, classe | Microsoft Docs"
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
  - "is_destructible"
  - "std.is_destructible"
  - "std::is_destructible"
  - "type_traits/std::is_destructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_destructible"
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_destructible, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est destructible.  
  
## Syntaxe  
  
```  
template <class T>  
    struct is_destructible;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type destructible. Sinon, sa valeur est false. Les types destructibles sont des types référence, des types d’objets et des types pour lesquels, pour un type `U` égal à `remove_all_extents_t<T>`, l’opérande non évalué `std::declval<U&>.~U()` est bien formé. D’autres types, notamment les types incomplets, `void`, et les types de fonction, ne sont pas des types destructibles.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)