---
title: "is_move_assignable (classe) | Microsoft Docs"
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
  - "is_move_assignable"
  - "std.is_move_assignable"
  - "std::is_move_assignable"
  - "type_traits/std::is_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_assignable"
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_move_assignable (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si le type peut être déplace attribué.  
  
## Syntaxe  
  
```  
template<class T>  
    struct is_move_assignable;  
```  
  
#### Paramètres  
 `T`  
 Type à interroger.  
  
## Notes  
 Un type est assignable déplacement si une référence rvalue au type peut être assignée à une référence au type. Le prédicat de type équivaut à `is_assignable<T&, T&&>`. Déplacer des types assignables incluent référençable types scalaires et les types de classe qui ont généré par le compilateur ou définis par l’utilisateur opérateurs d’assignation.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)