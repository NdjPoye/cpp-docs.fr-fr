---
title: "queue (STL/CLR) | Microsoft Docs"
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
  - "cliext::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/queue> (STL/CLR)"
  - "en-tête <queue> (STL/CLR)"
  - "queue (classe) (STL/CLR)"
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant le "premier entré, premier sorti" accès.  Vous utilisez l'adaptateur `queue` de conteneur pour gérer un conteneur sous\-jacent en file d'attente.  
  
 Dans la description du ci\-dessous, `GValue` est le même que `Value` sauf si ce dernier est un type de référence, auquel cas il s'agit `Value^`.  De même, `GContainer` est le même que `Container` sauf si ce dernier est un type de référence, auquel cas il s'agit `Container^`.  
  
## Syntaxe  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### Paramètres  
 Valeur  
 Type d'un élément dans la séquence contrôlée.  
  
 Conteneur  
 Type du conteneur sous\-jacent.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[queue::const\_reference](../dotnet/queue-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[queue::container\_type](../dotnet/queue-container-type-stl-clr.md)|Type du conteneur sous\-jacent.|  
|[queue::difference\_type](../dotnet/queue-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)|Le type de l'interface générique pour l'adaptateur de conteneur.|  
|[queue::generic\_value](../dotnet/queue-generic-value-stl-clr.md)|Le type d'un élément pour une utilisation avec l'interface générique pour l'adaptateur du conteneur.|  
|[queue::reference](../dotnet/queue-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[queue::size\_type](../dotnet/queue-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[queue::value\_type](../dotnet/queue-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonctions membres|Description|  
|-----------------------|-----------------|  
|[queue::assign](../dotnet/queue-assign-stl-clr.md)|Remplace tous les éléments.|  
|[queue::back](../dotnet/queue-back-stl-clr.md)|Accède au dernier élément.|  
|[queue::empty](../dotnet/queue-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[queue::front](../dotnet/queue-front-stl-clr.md)|Accède au premier élément.|  
|[queue::get\_container](../dotnet/queue-get-container-stl-clr.md)|Accède au conteneur sous\-jacent.|  
|[queue::pop](../dotnet/queue-pop-stl-clr.md)|Supprime le premier élément.|  
|[queue::push](../dotnet/queue-push-stl-clr.md)|Ajoute un nouveau dernier élément.|  
|[queue::queue](../dotnet/queue-queue-stl-clr.md)|Construit un objet container.|  
|[queue::size](../dotnet/queue-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[queue::to\_array](../dotnet/queue-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[queue::back\_item](../dotnet/queue-back-item-stl-clr.md)|Accède au dernier élément.|  
|[queue::front\_item](../dotnet/queue-front-item-stl-clr.md)|Accède au premier élément.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(queue\)](../dotnet/operator-inequality-queue-stl-clr.md)|Détermine si un objet de `queue` n'est pas égal à un autre objet de `queue`.|  
|[operator\< \(queue\)](../dotnet/operator-less-than-queue-stl-clr.md)|Détermine si un objet de `queue` est inférieur à un autre objet de `queue`.|  
|[operator\<\= \(queue\)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Détermine si un objet de `queue` est inférieur ou égal à un objet de `queue`.|  
|[operator\=\= \(queue\)](../dotnet/operator-equality-queue-stl-clr.md)|Détermine si un objet de `queue` n'est pas égal à un autre objet de `queue`.|  
|[operator\> \(queue\)](../dotnet/operator-greater-than-queue-stl-clr.md)|Détermine si un objet de `queue` est plus grand à un autre objet de `queue`.|  
|[operator\>\= \(queue\)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Détermine si un objet de `queue` est plus grand ou égal à un objet de `queue`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|IQueueValue\<, conteneur\>|Conserver l'adaptateur générique de conteneur.|  
  
## Notes  
 L'objet alloue et libère le stockage de la séquence qu'il contrôle par un conteneur sous\-jacent, de type `Container`, qui stocke les éléments de `Value` et développe à la demande.  L'objet limite l'accès uniquement à placer le premier élément et dépiler le dernier élément, l'implémentation d'une première \- file d'attente \(premier entré, premier sorti \(également appelé file d'attente FIFO, ou simplement une file d'attente\).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [pile](../dotnet/stack-stl-clr.md)   
 [vecteur](../dotnet/vector-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)