---
title: "collection_adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter (classe) (STL/CLR)"
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Encapsule une collection de .NET pour une utilisation comme conteneur STL ou CLR.  Une `collection_adapter` est une classe de modèle qui décrit un objet simple de conteneur STL ou CLR.  Elle inclut une interface de \(BCL\) de la bibliothèque de classes de base, et renvoie une paire d'itérateurs utilisée pour manipuler la séquence contrôlée.  
  
## Syntaxe  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### Paramètres  
 Coll  
 Le type de la collection encapsulée.  
  
## Spécialisations  
  
|Spécialisation|Description|  
|--------------------|-----------------|  
|IEnumerable|Parcoure les éléments.|  
|ICollection|Entretient un groupe d'éléments .|  
|IList|Entretient un ensemble ordonné d'éléments.|  
|IDictionary|Conservez un ensemble de paires {clé,valeur}.|  
|IEnumerable\<Value\>|Parcoure les éléments typés.|  
|ICollection\<Value\>|Maintient un groupe d'éléments typés.|  
|IList\<Value\>|Entretient un groupe ordonné d'éléments typés.|  
|IDictionary\<Value\>|Contient un ensemble de paires typées {clé,valeur}.|  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[collection\_adapter::difference\_type](../dotnet/collection-adapter-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[collection\_adapter::iterator](../dotnet/collection-adapter-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[collection\_adapter::key\_type](../dotnet/collection-adapter-key-type-stl-clr.md)|Le type de clé de dictionnaire.|  
|[collection\_adapter::mapped\_type](../dotnet/collection-adapter-mapped-type-stl-clr.md)|Le type de valeur du dictionnaire.|  
|[collection\_adapter::reference](../dotnet/collection-adapter-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[collection\_adapter::size\_type](../dotnet/collection-adapter-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[collection\_adapter::value\_type](../dotnet/collection-adapter-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)|Indique l'interface encapsulée de BCL.|  
|[collection\_adapter::begin](../dotnet/collection-adapter-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[collection\_adapter::collection\_adapter](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Construit un objet adaptateur.|  
|[collection\_adapter::end](../dotnet/collection-adapter-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[collection\_adapter::size](../dotnet/collection-adapter-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[collection\_adapter::swap](../dotnet/collection-adapter-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Remplace le descripteur BCL stocké.|  
  
## Notes  
 Vous utilisez cette classe de modèle pour manipuler un conteneur de BCL comme conteneur STL ou CLR.  Le `collection_adapter` enregistre un descripteur vers une interface de BCL, qui contrôle après une séquence d'éléments.  Un objet `X` d' `collection_adapter` renvoie une paire d'itérateurs d'entrée `X.begin()` et `X.end()` que vous utilisez pour visiter les éléments, dans l'ordre.  Certaines spécialisations vous permettent également d'écrire `X.size()` pour déterminer la longueur de la séquence contrôlée.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/adapter\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)