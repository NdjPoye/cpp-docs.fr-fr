---
title: "is_trivially_constructible (classe) | Microsoft Docs"
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
  - "is_trivially_constructible"
  - "std.is_trivially_constructible"
  - "std::is_trivially_constructible"
  - "type_traits/std::is_trivially_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_constructible"
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_constructible (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si un type est relativement constructible lorsque les types d’arguments spécifiés sont utilisés.  
  
## Syntaxe  
  
```  
template <class T, class... Args>  
    struct is_trivially_constructible;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
 `Args`  
 Les types d’arguments à faire correspondre dans un constructeur de `T`.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est simplement être construit en utilisant les types d’arguments dans `Args`, sinon sa valeur est false. Type `T` est relativement constructible si la définition de variable `T t(std::declval<Args>()...);` est bien formée et est connue pour n’appeler aucune opération non triviale. Les deux `T` et tous les types de `Args` doivent être des types complets, `void`, ou les tableaux de la limite est inconnue.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)