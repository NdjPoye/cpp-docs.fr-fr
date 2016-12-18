---
title: "priority_queue (STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/queue> (STL/CLR)"
  - "en-tête <queue> (STL/CLR)"
  - "priority_queue (classe) (STL/CLR)"
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence ordonnée de longueur variable d'éléments ayant un accès limité.  Vous utilisez l'adaptateur `priority_queue` de conteneur pour gérer un conteneur sous\-jacent en file de priorité.  
  
 Dans la description ci\-dessous, `GValue` est le même que `Value` sauf si ce dernier est un type de référence, auquel cas il vaut `Value^`.  De même, `GContainer` est le même que `Container` sauf si ce dernier est un type de référence, auquel cas il vaut `Container^`.  
  
## Syntaxe  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
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
|[priority\_queue::const\_reference](../dotnet/priority-queue-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[priority\_queue::container\_type](../dotnet/priority-queue-container-type-stl-clr.md)|Type du conteneur sous\-jacent.|  
|[priority\_queue::difference\_type](../dotnet/priority-queue-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)|Le type de l'interface générique pour l'adaptateur de conteneur.|  
|[priority\_queue::generic\_value](../dotnet/priority-queue-generic-value-stl-clr.md)|Le type d'un élément pour une utilisation avec l'interface générique pour l'adaptateur du conteneur.|  
|[priority\_queue::reference](../dotnet/priority-queue-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[priority\_queue::size\_type](../dotnet/priority-queue-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md)|Le délégué de classement pour deux éléments.|  
|[priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Méthode|Description|  
|-------------|-----------------|  
|[priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)|Remplace tous les éléments.|  
|[priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[priority\_queue::get\_container](../dotnet/priority-queue-get-container-stl-clr.md)|Accède au conteneur sous\-jacent.|  
|[priority\_queue::pop](../dotnet/priority-queue-pop-stl-clr.md)|Supprime l'élément de priorité maximale.|  
|[priority\_queue::priority\_queue](../dotnet/priority-queue-priority-queue-stl-clr.md)|Construit un objet container.|  
|[priority\_queue::push](../dotnet/priority-queue-push-stl-clr.md)|Ajoute un nouvel élément.|  
|[priority\_queue::size](../dotnet/priority-queue-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[priority\_queue::top](../dotnet/priority-queue-top-stl-clr.md)|Accède à l'élément ayant la priorité la plus élevée.|  
|[priority\_queue::to\_array](../dotnet/priority-queue-to-array-stl-clr.md)|Copie la séquence contrôlée dans un nouveau tableau.|  
|[priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)|Copie le délégué de classement pour deux éléments.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[priority\_queue::top\_item](../dotnet/priority-queue-top-item-stl-clr.md)|Accède à l'élément ayant la priorité la plus élevée.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[priority\_queue::operator\=](../dotnet/priority-queue-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|IPriorityQueue\<Value, Container\>|Conserver l'adaptateur générique de conteneur.|  
  
## Notes  
 L'objet alloue et libère le stockage de la séquence qu'il contrôle par un conteneur sous\-jacent, de type `Container`, qui stocke les éléments de `Value` et s'agrandit à la demande.  Il contient la séquence ordonnée en tant que tas, avec l'élément de priorité la plus élevée \(l'élément maximal\) facilement accessible et amovible.  L'objet limite l'accès à l'empilement de nouveaux éléments et le dépilement de l'élément le plus élevé uniquement, implémentant ainsi une file de priorité.  
  
 L'objet classifie la séquence qu'il contrôle en appelant un objet délégué stocké de type [priority\_queue::value\_compare](../dotnet/priority-queue-value-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stocké lorsque vous construisez la priority\_queue; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<(value_type, value_type)`.  Vous accédez à cet objet stocké en appelant la méthode [priority\_queue::value\_comp](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Un objet délégué de la sorte doit imposer un ordre strict faible sur les valeurs du type [priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `value_comp()(X, Y)` retourne le même résultat booléen à chaque appel.  
  
 Si `value_comp()(X, Y)` est vrai, alors `value_comp()(Y, X)` doit être faux.  
  
 Si `value_comp()(X, Y)` est vrai, alors on dit que `X` est trié avant `Y`.  
  
 Si `!value_comp()(X, Y) && !value_comp()(Y, X)` est vrai, alors `X` et `Y` ont un classement équivalent.  
  
 Pour n'importe quel élément `X` qui précède `Y` dans la séquence contrôlée, `key_comp()(Y, X)` est faux. \(Pour l'objet délégué par défaut, les clés ne perdent jamais en valeur.\)  
  
 L'élément le plus élevé est l'un des éléments qui n'est classé avant tout autre élément.  
  
 Étant donné que le conteneur sous\-jacent contient des éléments rangés en tas :  
  
 Le conteneur doit prendre en charge les itérateurs à accès aléatoire.  
  
 Les éléments d'ordre équivalent peuvent être dépilés dans un ordre différent que celui dans lequel ils ont été empilés. \(Le classement n'est pas stable.\)  
  
 Par conséquent, les candidats pour le conteneur sous\-jacent incluent [deque](../dotnet/deque-stl-clr.md) et [vecteur](../dotnet/vector-stl-clr.md).  
  
## Configuration requise  
 **En\-tête :** \<cliext\/queue\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [pile](../dotnet/stack-stl-clr.md)   
 [vecteur](../dotnet/vector-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)