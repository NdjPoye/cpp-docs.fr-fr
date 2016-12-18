---
title: "raw_storage_iterator, classe | Microsoft Docs"
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
  - "std::raw_storage_iterator"
  - "raw_storage_iterator"
  - "std.raw_storage_iterator"
  - "memory/std::raw_storage_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_storage_iterator (classe)"
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_storage_iterator, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe d'adaptateur fournie pour permettre aux algorithmes de stocker leurs résultats dans la mémoire non initialisée.  
  
## Syntaxe  
  
```  
  
        template <class   
        OutputIterator,  
         class   
        Type>  
class raw_storage_iterator  
```  
  
#### Paramètres  
 `OutputIterator`  
 Spécifie l'itérateur de sortie de l'objet stocké.  
  
 *Type*  
 Type d'objet pour lequel le stockage est alloué.  
  
## Notes  
 Cette classe décrit un itérateur de sortie qui construit des objets de type **Type** dans la séquence qu'il génère.  Un objet de classe `raw_storage_iterator`\<**ForwardIterator**, **Type**\> accède au stockage via un objet itérateur vers l'avant, de classe **ForwardIterator**, que vous spécifiez lors de la construction de l'objet.  Pour un objet first de classe **ForwardIterator**, l'expression **&\*first** doit désigner le stockage non construit pour l'objet suivant \(de type **Type**\) dans la séquence générée.  
  
 Cette classe d'adaptateur est utilisée quand il est nécessaire de séparer l'allocation de mémoire de la construction d'objet.  Le `raw_storage_iterator` peut être utilisé pour copier des objets dans le stockage non initialisé, comme la mémoire allouée à l'aide de la fonction `malloc`.  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[raw\_storage\_iterator](../Topic/raw_storage_iterator::raw_storage_iterator.md)|Construit un itérateur de stockage brut avec un itérateur de sortie sous\-jacent spécifié.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/raw_storage_iterator::element_type.md)|Fournit un type qui décrit un élément à stocker dans un itérateur de stockage brut.|  
|[iter\_type](../Topic/raw_storage_iterator::iter_type.md)|Fournit un type qui décrit un itérateur sous\-jacent à un itérateur de stockage brut.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*](../Topic/raw_storage_iterator::operator*.md)|Opérateur de suppression de référence utilisé pour implémenter l'expression d'itérateur de sortie \*`ii` \= `x`.|  
|[opérateur \=](../Topic/raw_storage_iterator::operator=.md)|Opérateur d'affectation utilisé pour implémenter l'expression d'itérateur de stockage brut \*`i` \= `x` pour le stockage en mémoire.|  
|[operator\+\+](../Topic/raw_storage_iterator::operator++.md)|Opérateurs de préincrémentation et de postincrémentation pour les itérateurs de stockage brut.|  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)