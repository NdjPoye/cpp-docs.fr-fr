---
title: "hash, structure | Microsoft Docs"
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
  - "typeindex/std::hash"
dev_langs: 
  - "C++"
ms.assetid: e5a41202-ef3b-45d0-b3a7-4c2dbdc0487a
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle définit sa méthode comme retournant `val.hash_code()`. La méthode définit une fonction de hachage qui est utilisée pour mapper les valeurs de type [type\_index](../standard-library/type-index-class.md) pour une distribution de valeurs d’index.  
  
## Syntaxe  
  
```vb  
template<>  
    struct hash<type_index>  
        : public unary_function<type_index, size_t>  
    { // hashes a typeinfo object  
    size_t operator()(type_index val) const;  
    };  
```  
  
## Voir aussi  
 [\<typeindex\>](../standard-library/typeindex.md)