---
title: "is_nothrow_copy_assignable, classe | Microsoft Docs"
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
  - "is_nothrow_copy_assignable"
  - "std.is_nothrow_copy_assignable"
  - "std::is_nothrow_copy_assignable"
  - "type_traits/std::is_nothrow_copy_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_copy_assignable"
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_nothrow_copy_assignable, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un opérateur d’assignation de copie qui est connu du compilateur ne pas à lever.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_nothrow_copy_assignable;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 S’applique une instance du prédicat de type pour un type référençable `T` où `is_nothrow_assignable<T&, const T&>` contient true ; sinon, sa valeur est false.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_nothrow\_assignable \(classe\)](../standard-library/is-nothrow-assignable-class.md)   
 [nothrow](../cpp/nothrow-cpp.md)