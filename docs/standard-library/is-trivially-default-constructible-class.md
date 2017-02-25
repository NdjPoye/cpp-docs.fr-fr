---
title: "is_trivially_default_constructible, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_trivially_default_constructible"
  - "std.is_trivially_default_constructible"
  - "std::is_trivially_default_constructible"
  - "type_traits/std::is_trivially_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_default_constructible"
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# is_trivially_default_constructible, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type a un constructeur par défaut trivial.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct  is_trivially_default_constructible;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 Une instance du prédicat de type a la valeur true si le type `Ty` est une classe qui a un constructeur trivial. Sinon, sa valeur est false.  
  
 Un constructeur par défaut pour une classe `Ty` est trivial si :  
  
-   il s'agit d'un constructeur par défaut déclaré implicitement ;  
  
-   la classe `Ty` n'a aucune fonction virtuelle ;  
  
-   la classe `Ty` n'a aucune base virtuelle ;  
  
-   toutes les bases directes de la classe `Ty` ont des constructeurs triviaux ;  
  
-   les classes de tous les membres de données non statiques de type de classe ont des constructeurs triviaux ;  
  
-   les classes de tous les membres de données non statiques de type tableau de classe ont des constructeurs triviaux.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)