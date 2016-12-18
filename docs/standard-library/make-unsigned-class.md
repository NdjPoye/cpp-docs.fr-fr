---
title: "make_unsigned, classe | Microsoft Docs"
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
  - "std.tr1.make_unsigned"
  - "make_unsigned"
  - "std::tr1::make_unsigned"
  - "std.make_unsigned"
  - "std::make_unsigned"
  - "type_traits/std::make_unsigned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_unsigned (classe)(TR1)"
  - "make_unsigned"
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# make_unsigned, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rend le type ou le plus petit type non signé supérieur ou égal en taille au type.  
  
## Syntaxe  
  
```  
template<class T>  
    struct make_unsigned;  
  
template<class T>  
    using make_unsigned_t = typename make_unsigned<T>::type;  
  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`T`|Type à modifier.|  
  
## Notes  
 Une instance du modificateur de type contient un type modifié qui est `T` si `is_unsigned<T>` contient la valeur true.  Dans le cas contraire, il s'agit du plus petit type signé `ST` pour lequel `sizeof (T) <= sizeof (ST)`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)