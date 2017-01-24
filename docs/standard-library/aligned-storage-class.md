---
title: "aligned_storage, classe | Microsoft Docs"
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
  - "aligned_storage"
  - "std::tr1::aligned_storage"
  - "std.tr1.aligned_storage"
  - "std.aligned_storage"
  - "std::aligned_storage"
  - "type_traits/std::aligned_storage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_storage (classe) (TR1)"
  - "aligned_storage"
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
caps.latest.revision: 23
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# aligned_storage, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un type correctement aligné.  
  
## Syntaxe  
  
```  
template<std::size_t Len, std::size_t Align>  
    struct aligned_storage;  
  
template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>  
    using aligned_storage_t = typename aligned_storage<Len, Align>::type;  
```  
  
#### Paramètres  
 `Len`  
 Taille de l'objet.  
  
 `Align`  
 Alignement de l'objet.  
  
## Notes  
 Le typedef de membre de modèle `type` est un synonyme pour un type POD avec l’alignement `Align` et taille `Len`.`Align` doit être égal à `alignment_of<T>::value` pour un certain type `T`, ou l’alignement par défaut.  
  
## Exemple  
  
```  
#include <type_traits>   
#include <iostream>   
  
typedef std::aligned_storage<sizeof (int),   
    std::alignment_of<double>::value>::type New_type;   
int main()   
    {   
    std::cout << "alignment_of<int> == "   
        << std::alignment_of<int>::value << std::endl;   
    std::cout << "aligned to double == "   
        << std::alignment_of<New_type>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
alignment_of < int > == 4 aligné à double == 8  
```  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of, classe](../standard-library/alignment-of-class.md)