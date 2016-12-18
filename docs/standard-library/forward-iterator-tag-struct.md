---
title: "forward_iterator_tag, struct | Microsoft Docs"
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
  - "std.forward_iterator_tag"
  - "forward_iterator_tag"
  - "std::forward_iterator_tag"
  - "xutility/std::forward_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_iterator_tag (classe)"
  - "forward_iterator_tag (struct)"
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# forward_iterator_tag, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur direct.  
  
## Syntaxe  
  
```  
  
   struct forward_iterator_tag  
: public input_iterator_tag {};  
```  
  
## Notes  
 Les classes d'indicateur de catégorie sont utilisées comme indicateurs de compilation pour la sélection d'algorithme.  La fonction de modèle doit découvrir quelle est la catégorie la plus spécifique de cet argument d'itérateur de façon à pouvoir utiliser l'algorithme le plus efficace lors de la compilation.  Pour chaque itération de type `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** doit être défini comme étant l'indicateur de catégorie le plus spécifique qui décrit le comportement de l'itérateur.  
  
 Le type est identique à **iterator**\<**Iter**\>**::iterator\_category** lorsque **Iter** décrit un objet pouvant servir d'itérateur par progression.  
  
## Exemple  
 Consultez [iterator\_traits](../standard-library/iterator-traits-struct.md) ou [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) pour un exemple d'utilisation de **iterator\_tag**S.  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [input\_iterator\_tag, struct](../standard-library/input-iterator-tag-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)