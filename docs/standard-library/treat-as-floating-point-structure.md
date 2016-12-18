---
title: "treat_as_floating_point, structure | Microsoft Docs"
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
  - "chrono/std::chrono::treat_as_floating_point"
dev_langs: 
  - "C++"
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# treat_as_floating_point, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie si `Rep` peut être considéré comme un type à virgule flottante.  
  
## Syntaxe  
  
```  
template<class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## Notes  
 Un `Rep` peut être considéré comme un type à virgule flottante uniquement lorsque la spécialisation `treat_as_floating_point<Rep>` est dérivée de [true\_type](../Topic/true_type%20Typedef.md).  La classe de modèle peut être spécialisée pour un type défini par l'utilisateur.  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)