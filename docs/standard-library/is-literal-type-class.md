---
title: "is_literal_type (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_literal_type"
  - "std.is_literal_type"
  - "std::is_literal_type"
  - "type_traits/std::is_literal_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_literal_type"
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_literal_type (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si un type peut être utilisé comme un `constexpr` variable ou être construit, utilisé par ou retournée à partir de `constexpr` fonctions.  
  
## Syntaxe  
  
```  
template <class T>  
    struct is_literal_type;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `T` est une *type de littéral*, sinon sa valeur est false. Un type de littéral est `void`, un type scalaire, un type référence, un tableau de type de littéral ou un type de classe littéral. Un type de classe littérale est un type de classe qui a un destructeur trivial, est un type d’agrégation ou a au moins un non\-déplacement, copie non `constexpr` constructeur et toutes ses classes de base et les données membres non static sont des types de littéral non volatile. Bien que le type d’un littéral est toujours un type de littéral, le concept d’un type de littéral inclut tout ce que le compilateur peut évaluer en tant qu’un `constexpr` au moment de la compilation.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)