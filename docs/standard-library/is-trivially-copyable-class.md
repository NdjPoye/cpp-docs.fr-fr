---
title: "is_trivially_copyable (classe) | Microsoft Docs"
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
  - "is_trivially_copyable"
  - "std.is_trivially_copyable"
  - "std::is_trivially_copyable"
  - "type_traits/std::is_trivially_copyable"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_copyable"
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copyable (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type est un type relativement reproductible.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_trivially_copyable;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est un type relativement reproductible, sinon sa valeur est false. Types simplement copiés ont sans opérations de copie non triviale, les opérations de déplacement ou de destructeurs. En règle générale, une opération de copie est considérée comme triviale si elle peut être implémentée comme une copie au niveau du bit. Les types intégrés et les tableaux de types plus simplement copiés sont simplement copiés.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)