---
title: "stack (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/stack> (STL/CLR)"
  - "en-tête <stack> (STL/CLR)"
  - "stack (classe) (STL/CLR)"
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant l'accès "premier entré, premier sorti".  Vous utilisez l'adaptateur `stack` de conteneur pour gérer un conteneur sous\-jacent comme pile de refoulement.  
  
 Dans la description ci\-dessous, `GValue` est le même que `Value` sauf si ce dernier est un type de référence, auquel cas il vaut `Value^`.  De même, `GContainer` est le même que `Container` sauf si ce dernier est un type de référence, auquel cas il vaut `Container^`.  
  
## Syntaxe  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
    { ..... };  
```  
  
#### Paramètres  
 Valeur  
 Type d'un élément dans la séquence contrôlée.  
  
 Conteneur  
 Type du conteneur sous\-jacent.  
  
## Membres  
  
|Définition de types|Description|  
|-------------------------|-----------------|  
|[stack::const\_reference](../dotnet/stack-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[stack::container\_type](../dotnet/stack-container-type-stl-clr.md)|Type du conteneur sous\-jacent.|  
|[stack::difference\_type](../dotnet/stack-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[stack::generic\_container](../dotnet/stack-generic-container-stl-clr.md)|Le type de l'interface générique pour l'adaptateur de conteneur.|  
|[stack::generic\_value](../dotnet/stack-generic-value-stl-clr.md)|Le type d'un élément pour une utilisation avec l'interface générique pour l'adaptateur du conteneur.|  
|[stack::reference](../dotnet/stack-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[stack::size\_type](../dotnet/stack-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[stack::value\_type](../dotnet/stack-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[stack::assign](../dotnet/stack-assign-stl-clr.md)|Remplace tous les éléments.|  
|[stack::empty](../dotnet/stack-empty-stl-clr.md)|Vérifie l'absence d'éléments.|  
|[stack::get\_container](../dotnet/stack-get-container-stl-clr.md)|Accède au conteneur sous\-jacent.|  
|[stack::pop](../dotnet/stack-pop-stl-clr.md)|Supprime le dernier élément.|  
|[stack::push](../dotnet/stack-push-stl-clr.md)|Ajoute un nouveau dernier élément.|  
|[stack::size](../dotnet/stack-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[stack::stack](../dotnet/stack-stack-stl-clr.md)|Construit un objet container.|  
|[stack::top](../dotnet/stack-top-stl-clr.md)|Accède au dernier élément.|  
|[stack::to\_array](../dotnet/stack-to-array-stl-clr.md)|Copie la séquence contrôlée dans un nouveau tableau.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[stack::top\_item](../dotnet/stack-top-item-stl-clr.md)|Accède au dernier élément.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)|Détermine si un objet de `stack` n'est pas égal à un autre objet de `stack`.|  
|[operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)|Détermine si un objet de `stack` est inférieur à un autre objet de `stack`.|  
|[operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Détermine si un objet de `stack` est inférieur ou égal à un objet de `stack`.|  
|[operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)|Détermine si un objet de `stack` n'est pas égal à un autre objet de `stack`.|  
|[operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)|Détermine si un objet de `stack` est plus grand qu'un autre objet de `stack`.|  
|[operator\>\= \(stack\)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Détermine si un objet de `stack` est supérieur ou égal à un objet de `stack`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|IStackValue\<, conteneur\>|Conserver l'adaptateur générique de conteneur.|  
  
## Notes  
 L'objet alloue et libère le stockage de la séquence qu'il contrôle par un conteneur sous\-jacent, de type `Container`, qui stocke les éléments de `Value` et s'agrandit à la demande.  L'objet limite l'accès à envoyer et dépiler uniquement le dernier élément, implémentation d'une file d'attente de type " dernier entré\-premier sortie " \(également appelé file d'attente de LIFO, ou la pile\).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/stack\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [vecteur](../dotnet/vector-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)