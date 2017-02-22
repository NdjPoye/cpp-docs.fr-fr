---
title: "input_iterator_tag, struct | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "input_iterator_tag"
  - "std.input_iterator_tag"
  - "std::input_iterator_tag"
  - "xutility/std::input_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "input_iterator_tag (classe)"
  - "input_iterator_tag (struct)"
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# input_iterator_tag, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe qui contient un type de retour de la fonction d'**iterator\_category** qui représente un itérateur d'entrée.  
  
## Syntaxe  
  
```  
  
struct input_iterator_tag {};  
  
```  
  
## Notes  
 Les classes d'un indicateur de catégorie sont utilisées comme indicateurs de compilation pour la sélection d'algorithme.  La fonction de modèle doit rechercher la catégorie le plus spécifique de cet argument d'itérateur de pouvoir utiliser l'algorithme le plus efficace de compilation.  Pour chaque itération de type `Iterator`, `iterator_traits`\<`Iterator`\>**::iterator\_category** doit être défini comme étant l'indicateur de catégorie le plus spécifique qui décrit le comportement de l'itérateur.  
  
 Le type est identique à **iterator**\<**Iter**\>**::iterator\_category** lorsque **Iter** décrit un objet pouvant servir d'itérateur d'entrée.  
  
## Exemple  
 Consultez [iterator\_traits](../standard-library/iterator-traits-struct.md) ou l'[random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) pour un exemple d'utilisation **iterator\_tag**S.  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)