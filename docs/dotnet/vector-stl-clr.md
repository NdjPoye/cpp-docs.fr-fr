---
title: "vector (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/vector> (STL/CLR)"
  - "en-tête <vector> (STL/CLR)"
  - "vecteur (classe) (STL/CLR)"
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant un accès aléatoire.  Vous utilisez le conteneur `vector` pour gérer une séquence d'éléments comme un bloc contigu de stockage.  Le bloc est implémenté en tant que tableau qui s'étend à la demande.  
  
 Dans la description ci\-dessous, `GValue` est le même que `Value` sauf si ce dernier est un type de référence, auquel cas il vaut `Value^`.  
  
## Syntaxe  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Valeur  
 Type d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[vector::const\_reference](../dotnet/vector-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[vector::difference\_type](../dotnet/vector-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[vector::generic\_iterator](../dotnet/vector-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[vector::generic\_reverse\_iterator](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[vector::generic\_value](../dotnet/vector-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[vector::iterator](../dotnet/vector-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[vector::reference](../dotnet/vector-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[vector::reverse\_iterator](../dotnet/vector-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[vector::size\_type](../dotnet/vector-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[vector::value\_type](../dotnet/vector-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[vector::assign](../dotnet/vector-assign-stl-clr.md)|Remplace tous les éléments.|  
|[vector::at](../dotnet/vector-at-stl-clr.md)|Accède à un élément ayant une position spécifiée.|  
|[vector::back](../dotnet/vector-back-stl-clr.md)|Accède au dernier élément.|  
|[vector::begin](../dotnet/vector-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[vector::capacity](../dotnet/vector-capacity-stl-clr.md)|Signale la taille de l'espace de stockage alloué pour le conteneur.|  
|[vector::clear](../dotnet/vector-clear-stl-clr.md)|Supprime tous les éléments.|  
|[vector::empty](../dotnet/vector-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[vector::end](../dotnet/vector-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[vector::erase](../dotnet/vector-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[vector::front](../dotnet/vector-front-stl-clr.md)|Accède au premier élément.|  
|[vector::insert](../dotnet/vector-insert-stl-clr.md)|Ajoute les éléments à une position spécifiée.|  
|[vector::pop\_back](../dotnet/vector-pop-back-stl-clr.md)|Supprime le dernier élément.|  
|[vector::push\_back](../dotnet/vector-push-back-stl-clr.md)|Ajoute un nouveau dernier élément.|  
|[vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[vector::rend](../dotnet/vector-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[vector::reserve](../dotnet/vector-reserve-stl-clr.md)|Garantit une capacité minimale de croissance pour le conteneur.|  
|[vector::resize](../dotnet/vector-resize-stl-clr.md)|Change le nombre d'éléments.|  
|[vector::size](../dotnet/vector-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[vector::swap](../dotnet/vector-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[vector::to\_array](../dotnet/vector-to-array-stl-clr.md)|Copie la séquence contrôlée dans un nouveau tableau.|  
|[vector::vector](../dotnet/vector-vector-stl-clr.md)|Construit un objet container.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[vector::back\_item](../dotnet/vector-back-item-stl-clr.md)|Accède au dernier élément.|  
|[vector::front\_item](../dotnet/vector-front-item-stl-clr.md)|Accède au premier élément.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[vector::operator](../dotnet/vector-operator-stl-clr.md)|Accède à un élément ayant une position spécifiée.|  
|[operator\!\= \(vector\)](../dotnet/operator-inequality-vector-stl-clr.md)|Détermine si un objet de `vector` n'est pas égal à un autre objet de `vector`.|  
|[operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)|Détermine si un objet de `vector` est inférieur à un autre objet de `vector`.|  
|[operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Détermine si un objet de `vector` est inférieur ou égal à un objet de `vector`.|  
|[operator\=\= \(vector\)](../dotnet/operator-equality-vector-stl-clr.md)|Détermine si un objet de `vector` n'est pas égal à un autre objet de `vector`.|  
|[operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)|Détermine si un objet de `vector` est plus grand qu'un autre objet de `vector`.|  
|[operator\>\= \(vector\)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Détermine si un objet de `vector` est supérieur ou égal à un objet de `vector`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Parcourir les éléments.|  
|<xref:System.Collections.ICollection>|Maintenir le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Parcourir les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintenir le groupe d'éléments typés.|  
|<xref:System.Collections.Generic.IList%601>|Gardez le groupe ordonné d'éléments typés.|  
|IVector\<Value\>|Maintenir le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère le stockage de la séquence qu'il contrôle avec un tableau d'éléments de `Value`, qui s'étend à la demande.  La croissance se produit de sorte que le coût d'ajout d'un nouvel élément est de temps fixe amorti.  En d'autres termes, le coût d'ajout d'éléments de la collection n'augmente pas, en moyenne, car la longueur de la séquence contrôlée est plus grande.  Par conséquent, un vecteur est un bon exemple de conteneur sous\-jacent de la classe de modèle [pile](../dotnet/stack-stl-clr.md).  
  
 Un `vector` prend en charge les itérateurs à accès aléatoire, ce qui signifie que vous pouvez faire référence à un élément en donnant directement sa position numérique, en partant de zéro pour le premier élément \(avant\), jusqu'à [vector::size](../dotnet/vector-size-stl-clr.md)`() - 1` pour le dernier élément \(arrière\).  Cela signifie également qu'un vecteur est un bon exemple de conteneur sous\-jacent de la classe de modèle [priority\_queue](../dotnet/priority-queue-stl-clr.md).  
  
 Un itérateur de vecteur enregistre une gestion de l'objet vecteur associé, ainsi que le décalage de l'élément qu'elle pointe.  Vous pouvez utiliser des itérateurs uniquement avec leurs objets conteneurs associés.  Le décalage d'un élément vectoriel est identique à sa place.  
  
 Insérer ou effacer les éléments peut modifier la valeur de l'élément stocké à une position spécifiée, la valeur indiquée par un itérateur peut également changer. \(Le conteneur peut avoir à copier des éléments vers le haut ou le bas pour créer un trou avant l'insertion ou de remplir un trou après un effacement.\) Cependant, un itérateur vectoriel reste valide à condition que le décalage soit compris dans la plage `[0,` [vector::size](../dotnet/vector-size-stl-clr.md)`()]`.  De plus, un itérateur valide reste déréférençable \-\- vous pouvez l'utiliser pour accéder ou modifier la valeur de l'élément qu'il indique \-\- tant que son décalage n'est pas égal à `size()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne détruit `not` ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/vector\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [pile](../dotnet/stack-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)