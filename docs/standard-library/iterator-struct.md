---
title: "iterator, struct | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator"
  - "std::iterator"
  - "std.iterator"
  - "xutility/std::iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator (classe)"
  - "iterator (struct)"
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# iterator, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une structure de base vide utilisé pour garantir qu'une classe définie par l'utilisateur d'itérateur fonctionne correctement avec **iterator\_trait**S.  
  
## Syntaxe  
  
```  
template<class Category, class Type, class Distance = ptrdiff_t  
    class Pointer = Type*, class Reference = Type&>  
    struct iterator {  
        typedef Category iterator_category;  
        typedef Type value_type;  
        typedef Distance difference_type;  
        typedef Distance distance_type;  
        typedef Pointer pointer;  
        typedef Reference reference;  
    };  
```  
  
## Notes  
 La structure de modèle sert de type de base pour tous les itérateurs.  Il définit les types de membres  
  
-   `iterator_category` \(un synonyme pour le paramètre `Category`de modèle\).  
  
-   `value_type` \(un synonyme pour le paramètre **Type**de modèle\).  
  
-   `difference_type` \(un synonyme pour le paramètre `Distance`de modèle\).  
  
-   `distance_type` \(un synonyme pour le paramètre `Distance`de modèles\)  
  
-   `pointer` \(un synonyme pour le paramètre `Pointer`de modèle\).  
  
-   `reference` \(un synonyme pour le paramètre `Reference`de modèle\).  
  
 Notez qu' `value_type` ne doit pas être un type de constante même si les points de **pointer** à un objet de **Type** const et de référence indique un objet de **Type**const.  
  
## Exemple  
 Voir le [iterator\_traits](../standard-library/iterator-traits-struct.md) pour obtenir un exemple de la façon dont déclarer et utiliser les types dans la classe de base d'itération.  
  
## Configuration requise  
 itérateur\<de**En\-tête :** \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<iterator\>](../standard-library/iterator.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)