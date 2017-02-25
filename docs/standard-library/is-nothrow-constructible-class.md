---
title: "is_nothrow_constructible (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_constructible (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si un type peut être construit et ne connaît ne pas lever lorsque les types d’arguments spécifiés sont utilisés.  
  
## Syntaxe  
  
```  
template <class T, class... Args>  
    struct is_nothrow_constructible;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Les types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` ne peut être construit en utilisant les types d’arguments dans `Args`, et le constructeur est connu par le compilateur ne pas lever ; sinon, sa valeur est false. Type `T` constructible si la définition de variable `T t(std::declval<Args>()...);` est bien formé. Les deux `T` et tous les types de `Args` doivent être des types complets, `void`, ou les tableaux de la limite est inconnue.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)