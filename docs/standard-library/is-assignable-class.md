---
title: "is_assignable (classe) | Microsoft Docs"
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
  - "is_assignable"
  - "std.is_assignable"
  - "std::is_assignable"
  - "type_traits/std::is_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_assignable"
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_assignable (classe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste si une valeur de `From` type peut être affecté à un `To` type.  
  
## Syntaxe  
  
```  
template <class To, class From>  
    struct is_assignable;  
```  
  
#### Paramètres  
 Pour  
 Type de l'objet qui reçoit l'assignation.  
  
 From  
 Type de l'objet qui fournit la valeur.  
  
## Notes  
 L’expression non évaluée `declval<To>() = declval<From>()` doit être correctement construit. Les deux `From` et `To` doivent être des types complets, `void`, ou les tableaux de la limite est inconnue.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)