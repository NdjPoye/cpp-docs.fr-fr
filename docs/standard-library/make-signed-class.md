---
title: "make_signed, classe | Microsoft Docs"
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
  - "std::tr1::make_signed"
  - "make_signed"
  - "std.tr1.make_signed"
  - "std.make_signed"
  - "std::make_signed"
  - "type_traits/std::make_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_signed (classe)(TR1)"
  - "make_signed"
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# make_signed, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rend le type ou le plus petit type signé supérieur ou égal en taille au type.  
  
## Syntaxe  
  
```  
template<class T>  
    struct make_signed;  
  
template<class T>  
    using make_signed_t = typename make_signed<T>::type;  
```  
  
#### Paramètres  
 `T`  
 Type à modifier.  
  
## Notes  
 Une instance du modificateur de type contient un type modifié qui est `T` si `is_signed<T>` contient la valeur true. Dans le cas contraire, il s'agit du plus petit type non signé `UT` pour lequel `sizeof (T) <= sizeof (UT)`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)