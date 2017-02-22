---
title: "initializer_list Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# initializer_list Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit l'accès à un tableau d'éléments dans lequel chaque membre est du type spécifié.  
  
## Syntaxe  
  
```cpp  
template<  
    class Type >  
    class initializer_list  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Elem`|Type de données d'élément à stocker dans le `initializer_list`.|  
|`_First`|Pointeur vers le premier élément du `initializer_list`.|  
|`_Last`|Pointeur vers le dernier élément du `initializer_list`.|  
  
## Notes  
 Un `initializer_list` peut être construit à l'aide d'une liste d'initialiseurs entre accolades :  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 Le compilateur transforme les listes d'initialiseurs entre accolades avec des éléments homogènes en un `initializer_list` chaque fois que la signature de fonction nécessite un `initializer_list`.  Pour plus d'informations sur l'utilisation de `initializer_list`, consultez [Constructeurs d'initialisation uniforme et de délégation](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[initializer\_list](../Topic/forward_list::forward_list.md)|Construit un objet de type `initializer_list`.|  
  
### Typedefs  
  
|||  
|-|-|  
|value\_type|Type des éléments dans le `initializer_list`.|  
|reference|Type qui fournit une référence à un élément stocké dans le `initializer_list`.|  
|const\_reference|Type qui fournit une référence constante à un élément dans le `initializer_list`.|  
|size\_type|Type qui représente le nombre d'éléments dans le `initializer_list`.|  
|iterator|Type qui fournit un itérateur pour le `initializer_list`.|  
|const\_iterator|Type qui fournit un itérateur constant pour le `initializer_list`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[begin](../Topic/initializer_list::begin.md)|Retourne un pointeur vers le premier élément d'un `initializer_list`.|  
|[end](../Topic/initializer_list::end.md)|Retourne un pointeur vers la position au\-delà du dernier élément dans un `initializer_list`.|  
|[size](../Topic/initializer_list::size.md)|Retourne le nombre d'éléments d'un `initializer_list`.|  
  
## Configuration requise  
 **En\-tête :** \<initializer\_list\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<forward\_list\>](../standard-library/forward-list.md)