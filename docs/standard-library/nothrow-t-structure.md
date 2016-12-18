---
title: "nothrow_t, structure | Microsoft Docs"
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
  - "nothrow_t"
  - "std.nothrow_t"
  - "std::nothrow_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nothrow_t (classe)"
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# nothrow_t, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le struct est utilisé comme paramètre de fonction à l'opérateur nouveau pour indiquer que la fonction doit retourner un pointeur null pour stocker un échec d'allocation, plutôt que lèvent une exception.  
  
## Syntaxe  
  
```  
struct std::nothrow_t {};  
```  
  
## Notes  
 Le struct aide de le compilateur de sélectionner la version correcte du constructeur.  [nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md) est un synonyme pour les objets de type `std::nothrow_t`.  
  
## Exemple  
 Consultez [opérateur nouveau](../Topic/operator%20new%20\(%3Cnew%3E\).md) et l'[opérateur nouveau &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) pour obtenir des exemples de la manière dont `std::nothrow_t` est utilisé comme paramètre de fonction.  
  
## Configuration requise  
 **En\-tête :** \<nouveau\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)