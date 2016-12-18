---
title: "conditional, classe | Microsoft Docs"
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
  - "std::tr1::conditional"
  - "std.tr1.conditional"
  - "conditional"
  - "std.conditional"
  - "std::conditional"
  - "type_traits/std::conditional"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conditional (classe) (TR1)"
  - "conditional"
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# conditional, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sélectionne un des deux types, selon la condition spécifiée.  
  
## Syntaxe  
  
```  
template <bool B, class T1, class T2>  
    struct conditional;  
  
template <bool _Test, class _T1, class _T2>  
    using conditional_t = typename conditional<_Test, _T1, _T2>::type;  
```  
  
#### Paramètres  
 `B`  
 Valeur qui détermine le type sélectionné.  
  
 `T1`  
 Résultat de type quand B a la valeur true.  
  
 `T2`  
 Résultat de type quand B a la valeur false.  
  
## Notes  
 Le typedef de membre de modèle `conditional<B, T1, T2>::type` équivaut à `T1` quand `B` équivaut à `true`, et équivaut à `T2` quand `B` équivaut à `false`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)