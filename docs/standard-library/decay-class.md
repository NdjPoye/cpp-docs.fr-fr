---
title: "decay, classe | Microsoft Docs"
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
  - "decay"
  - "std.tr1.decay"
  - "std::tr1::decay"
  - "std.decay"
  - "std::decay"
  - "type_traits/std::decay"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decay (classe)(TR1)"
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# decay, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère le type passés par valeur. Effectue le type sans référence, non const, non volatile, ou un pointeur vers le type à partir d’une fonction ou un type de tableau.  
  
## Syntaxe  
  
```  
template<class T>  
    struct decay;  
  
template<class T> using decay_t = typename decay<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Utilisez le modèle d’atténuation pour générer le type résultant comme si le type a été passé par valeur en tant qu’argument. Le typedef de membre de classe de modèle `type` contient un type modifié qui est défini dans les étapes suivantes :  
  
-   Le type `U` est défini en tant que `remove_reference<T>::type`.  
  
-   Si `is_array<U>::value` est true, le type modifié `type` est `remove_extent<U>::type *`.  
  
-   Sinon, si `is_function<U>::value` est true, le type modifié `type` est `add_pointer<U>::type`.  
  
-   Dans le cas contraire, le type modifié `type` est `remove_cv<U>::type`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)