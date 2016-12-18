---
title: "is_final (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_final"
  - "std.is_final"
  - "std::is_final"
  - "type_traits/std::is_final"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_final"
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_final (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est un type de classe marqué `final`.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_final;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type de classe marqué `final`, sinon sa valeur est false. Si `T` est un type de classe, il doit être un type complet.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Spécificateur final](../cpp/final-specifier.md)