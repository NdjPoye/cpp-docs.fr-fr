---
title: "is_trivially_copy_assignable | Microsoft Docs"
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
  - "is_trivially_copy_assignable"
  - "std.is_trivially_copy_assignable"
  - "std::is_trivially_copy_assignable"
  - "type_traits/std::is_trivially_copy_assignable"
dev_langs: 
  - "C++"
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un opérateur d'assignation de copie trivial.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_trivially_copy_constructible;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un opérateur d'assignation de copie trivial. Sinon, sa valeur est false.  
  
 Un constructeur d'assignation pour une classe `Ty` est trivial si :  
  
 il est fourni implicitement ;  
  
 la classe `Ty` n'a aucune fonction virtuelle ;  
  
 la classe `Ty` n'a aucune base virtuelle ;  
  
 les classes de tous les membres de données non statiques de type classe possèdent des opérateurs d'assignation triviaux ;  
  
 les classes de tous les membres de données non statiques de type tableau de classe possèdent des opérateurs d'assignation triviaux.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)