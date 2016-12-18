---
title: "is_trivially_move_constructible (classe) | Microsoft Docs"
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
  - "is_trivially_move_constructible"
  - "std.is_trivially_move_constructible"
  - "std::is_trivially_move_constructible"
  - "type_traits/std::is_trivially_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_move_constructible"
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_move_constructible (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un constructeur de déplacement trivial.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct is_trivially_move_constructible;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur de déplacement trivial. Sinon, sa valeur est false.  
  
 Un constructeur de déplacement pour une classe `Ty` est trivial si :  
  
 il est déclaré implicitement ;  
  
 ses types de paramètres sont équivalents à ceux d'une déclaration implicite ;  
  
 la classe `Ty` n'a aucune fonction virtuelle ;  
  
 la classe `Ty` n'a aucune base virtuelle ;  
  
 la classe n'a aucun membre de données non statique volatile ;  
  
 toutes les bases directes de la classe `Ty` ont des constructeurs de déplacement triviaux ;  
  
 les classes de tous les membres de données non statiques de type de classe ont des constructeurs de déplacement triviaux ;  
  
 les classes de tous les membres de données non statiques de type tableau de classe ont des constructeurs de déplacement triviaux.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)