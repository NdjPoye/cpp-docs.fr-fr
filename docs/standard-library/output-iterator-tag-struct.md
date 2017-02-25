---
title: "output_iterator_tag, struct | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::output_iterator_tag"
  - "output_iterator_tag"
  - "xutility/std::output_iterator_tag"
  - "std.output_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "output_iterator_tag (classe)"
  - "output_iterator_tag (struct)"
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# output_iterator_tag, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui fournit un type de retour pour une fonction **iterator\_category** représentant un itérateur de sortie.  
  
## Syntaxe  
  
```  
  
struct output_iterator_tag {};  
  
```  
  
## Notes  
 Les classes de balise de catégorie sont utilisés comme compiler des balises pour la sélection de l’algorithme. La fonction de modèle doit rechercher la catégorie la plus spécifique de l’argument de l’itérateur afin qu’il puisse utiliser l’algorithme plus efficace au moment de la compilation. Pour chaque itérateur de type `Iterator`, `iterator_traits`\<`Iterator`\>**:: iterator\_category** doit être défini pour être la balise de catégorie plus spécifique qui décrit le comportement de l’itérateur.  
  
 Le type est le même que **itérateur**\<**Iter**\>**:: iterator\_category** lorsque **Iter** décrit un objet pouvant servir d’un itérateur de sortie.  
  
 Cette balise n’est pas paramétrable sur la `value_type` ou `difference_type` pour l’itérateur, comme avec les autres balises itérateur, car les itérateurs de sortie n’ont pas l’un `value_type` ou un `difference_type`.  
  
## Exemple  
 Consultez la page [iterator\_traits](../standard-library/iterator-traits-struct.md) ou [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) pour obtenir un exemple montrant comment utiliser **iterator\_tag**s.  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)