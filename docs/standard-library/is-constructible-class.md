---
title: "is_constructible (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_constructible"
  - "std.is_constructible"
  - "std::is_constructible"
  - "type_traits/std::is_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_constructible"
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# is_constructible (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si un type est constructible lorsque les types d’arguments spécifiés sont utilisés.  
  
## Syntaxe  
  
```  
template <class T, class... Args>  
    struct is_constructible;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Les types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` ne peut être construit en utilisant les types d’arguments dans `Args`, sinon sa valeur est false. Type `T` constructible si la définition de variable `T t(std::declval<Args>()...);` est bien formé. Les deux `T` et tous les types de `Args` doivent être des types complets, `void`, ou les tableaux de la limite est inconnue.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)