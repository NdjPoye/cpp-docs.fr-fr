---
title: "allocator&lt;void&gt;, classe | Microsoft Docs"
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
  - "memory/std::allocator<void>"
  - "std::allocator<void>"
  - "std.allocator<void>"
  - "allocator<void>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator<void> (classe)"
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator&lt;void&gt;, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une spécialisation de l'allocateur de classe du modèle en `void`, en définissant des types qui est logique dans ce contexte.  
  
## Syntaxe  
  
```  
template<>  
   class allocator<void> {  
   typedef void *pointer;  
   typedef const void *const_pointer;  
   typedef void value_type;  
   template<class Other>  
      struct rebind;  
   allocator( );  
   allocator(  
      const allocator<void>&  
   );  
   template<class Other>  
      allocator(  
         const allocator<Other>&  
      );  
   template<class Other>  
      allocator<void>& operator=(  
         const allocator<Other>&  
      );  
   };  
```  
  
## Notes  
 La classe spécialise explicitement la classe de modèle [allocateur](../standard-library/allocator-class.md) pour *void*de type. Les constructeurs et opérateur d'assignation se comportent de la même manière que pour la classe du modèle, mais elle identifie les types suivants :  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md).  
  
-   [pointeur](../Topic/allocator::pointer.md).  
  
-   [value\_type](../Topic/allocator::value_type.md).  
  
-   [reliez\-vous de nouveau](../Topic/allocator::rebind.md), une classe de modèle imbriquée.  
  
## Configuration requise  
 mémoire\<de**En\-tête :** \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)