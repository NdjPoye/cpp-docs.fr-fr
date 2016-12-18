---
title: "Collections et &#233;num&#233;rateurs ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection (interfaces)"
  - "collections, ATL (classes)"
  - "énumérateur (interfaces)"
  - "énumérateurs, ATL (classes)"
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Collections et &#233;num&#233;rateurs ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`collection` est un objet COM qui fournit une interface qui permet l'accès à un groupe d'éléments de données \(des données brutes ou d'autres objets\).  Une interface qui suit les normes pour permettre l'accès à un groupe d'objets est appelé *une interface de la collection*.  
  
 Au minimum, les interfaces de collection doivent fournir une propriété de **Nombre** qui retourne le nombre d'éléments dans la collection, une propriété de **Élément** qui retourne un élément de la collection sur un index, et une propriété d' `_NewEnum` qui retourne un énumérateur pour la collection.  Éventuellement, les interfaces de collection peuvent fournir **Ajouter** les méthodes et de **Supprimer** pour permettre à des éléments à insérer dans ou être supprimés de la collection, et une méthode de **Clear** pour supprimer tous les éléments.  
  
 `enumerator` est un objet COM qui fournit une interface pour itérer au sein de les éléments d'une collection.  Les interfaces d'énumérateurs fournissent un accès séquentiel aux éléments d'une collection via quatre méthodes requises : `Next`, **Ignorer**, **Réinitialiser**, et `Clone`.  
  
 Vous pouvez en savoir plus sur les interfaces d'énumérateur en lisant sur l'interface archétypale \(mais entièrement imaginaire\) de.  
  
## Dans cette section  
 [Classes de collection et d'énumérateur ATL](../atl/atl-collection-and-enumerator-classes.md)  
 Décrit brièvement et fournit des liens vers des classes ATL qui vous aideront les collections et des énumérateurs d'implémenter.  
  
 [Principes de conception pour les interfaces de collection et d'énumérateur](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 Présente les différents principes de conception derrière chaque type d'interface.  
  
 [implémenter une collection STL\-Basée](../atl/implementing-an-stl-based-collection.md)  
 Un exemple étendu qui vous présente l'implémentation d'une collection basée sur de \(STL\) Standard Template Library\).  
  
## Rubriques connexes  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fournit des liens vers des rubriques conceptuelles sur comment programmer avec la bibliothèque ATL.  
  
 [ATLCollections](../top/visual-cpp-samples.md)  
 Un exemple qui illustre l'utilisation d' `ICollectionOnSTLImpl` et d' `CComEnumOnSTL`, et l'implémentation de la stratégie de copie personnalisées.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)