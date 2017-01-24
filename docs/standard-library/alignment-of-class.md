---
title: "alignment_of, classe | Microsoft Docs"
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
  - "std.tr1.alignment_of"
  - "std::tr1::alignment_of"
  - "alignment_of"
  - "std.alignment_of"
  - "std::alignment_of"
  - "type_traits/std::alignment_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "alignment_of (classe) (TR1)"
  - "alignment_of"
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alignment_of, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient l'alignement du type spécifié.  Ce struct est implémenté en termes de [alignof](../cpp/alignof-and-alignas-cpp.md).  Utilisez `alignof` directement quand vous devez simplement interroger une valeur d'alignement.  Utilisez alignment\_of quand vous avez besoin d'une constante intégrale, par exemple lors de la répartition de balises.  
  
## Syntaxe  
  
```  
template<class Ty>  
    struct alignment_of;  
```  
  
#### Paramètres  
 `Ty`  
 Type à interroger.  
  
## Notes  
 La requête de type contient la valeur de l'alignement du type `Ty`.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [aligned\_storage, classe](../standard-library/aligned-storage-class.md)