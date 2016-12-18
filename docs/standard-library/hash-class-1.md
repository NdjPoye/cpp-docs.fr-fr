---
title: "hash, classe | Microsoft Docs"
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
  - "std.hash"
  - "xfunctional/std::hash"
  - "hash"
  - "typeindex/std::hash"
  - "std::hash"
  - "std.tr1.hash"
  - "std::tr1::hash"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash (classe)"
  - "hash (classe) (TR1)"
ms.assetid: e1b500c6-a5c8-4f6f-ad33-7ec52eb8e2e4
caps.latest.revision: 21
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Calcule le code de hachage d'une valeur.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct hash  
        : public unary_function<Ty, size_t> {  
    size_t operator()(Ty _Val) const;  
    };  
```  
  
## Notes  
 La fonction membre définit une fonction de hachage, appropriée pour mapper les valeurs de type `Ty` à une distribution de valeurs d'index.  L'opérateur membre retourne le code de hachage pour `_Val`, approprié à utiliser avec des classes du modèle `unordered_map`, `unordered_multimap`, `unordered_set`, et `unordered_multiset`.  `Ty` peut être n'importe quel type scalaire, `string`, `wstring`, `error_code`, `error_condition`, `u16string`, ou `u32string`.  
  
## Exemple  
  
```  
// std_tr1__functional__hash.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
#include <unordered_set>   
  
int main()   
    {   
    std::unordered_set<int, std::hash<int> > c0;   
    c0.insert(3);   
    std::cout << *c0.find(3) << std::endl;   
  
    return (0);   
    }  
  
```  
  
 **3**   
## Configuration requise  
 **En\-tête :** \<functional\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [unordered\_multimap, classe](../standard-library/unordered-multimap-class.md)   
 [unordered\_multiset, classe](../standard-library/unordered-multiset-class.md)   
 [\<unordered\_set\>](../standard-library/unordered-set.md)