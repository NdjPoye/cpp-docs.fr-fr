---
title: "bidirectional_iterator_tag, struct | Microsoft Docs"
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
  - "xutility/std::bidirectional_iterator_tag"
  - "std::bidirectional_iterator_tag"
  - "std.bidirectional_iterator_tag"
  - "bidirectional_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bidirectional_iterator_tag (classe)"
  - "bidirectional_iterator_tag (struct)"
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bidirectional_iterator_tag, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe qui contient un type de retour de la fonction d'**iterator\_category** qui représente un itérateur bidirectionnel.  
  
## Syntaxe  
  
```  
  
   struct bidirectional_iterator_tag  
: public forward_iterator_tag {};  
```  
  
## Notes  
 Les classes d'un indicateur de catégorie sont utilisées comme indicateurs de compilation pour la sélection d'algorithme.  La fonction de modèle doit rechercher la catégorie le plus spécifique de l'argument itérateur, afin de pouvoir utiliser l'algorithme le plus efficace de compilation.  Pour chaque itération de type `Iterator`, le ::\<**iterator\_category** d'`iterator_traits``Iterator`\>doit être défini comme étant l'indicateur de catégorie le plus spécifique qui décrit le comportement de l'itérateur.  
  
 Le type est le même que le\<::**iterator\_category** d'**iteratorIter**\>lorsque **Iter** décrit un objet pouvant servir d'itérateur bidirectionnel.  
  
## Exemple  
 Voir le [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) pour un exemple d'utilisation `bidirectional_iterator_tag`.  
  
## Configuration requise  
 **En\-tête :** \<iterator\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [forward\_iterator\_tag, struct](../standard-library/forward-iterator-tag-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)