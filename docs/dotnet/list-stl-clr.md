---
title: "list (STL/CLR) | Microsoft Docs"
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
  - "cliext::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/list> (STL/CLR)"
  - "en-tête <list> (STL/CLR)"
  - "list (classe) (STL/CLR)"
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `list` pour gérer une séquence d'éléments sous forme de liste liée bidirectionnelle de nœuds, stockant chacun un élément.  
  
 Dans la description ci\-dessous, `GValue` est le même que `Value` sauf si ce dernier est un type de référence, auquel cas il s'agit `Value^`.  
  
## Syntaxe  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Valeur  
 Type d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[list::const\_reference](../dotnet/list-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[list::difference\_type](../dotnet/list-difference-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[list::generic\_container](../dotnet/list-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[list::generic\_iterator](../dotnet/list-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[list::generic\_value](../dotnet/list-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[list::iterator](../dotnet/list-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[list::reference](../dotnet/list-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[list::reverse\_iterator](../dotnet/list-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[list::size\_type](../dotnet/list-size-type-stl-clr.md)|Type d'une distance signée entre deux éléments.|  
|[list::value\_type](../dotnet/list-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[list::assign](../dotnet/list-assign-stl-clr.md)|Remplace tous les éléments.|  
|[list::back](../dotnet/list-back-stl-clr.md)|Accède au dernier élément.|  
|[list::begin](../dotnet/list-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[list::clear](../dotnet/list-clear-stl-clr.md)|Supprime tous les éléments.|  
|[list::empty](../dotnet/list-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[list::end](../dotnet/list-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[list::erase](../dotnet/list-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[list::front](../dotnet/list-front-stl-clr.md)|Accède au premier élément.|  
|[list::insert](../dotnet/list-insert-stl-clr.md)|Ajoute les éléments à une position spécifiée.|  
|[list::list](../dotnet/list-list-stl-clr.md)|Construit un objet container.|  
|[list::merge](../dotnet/list-merge-stl-clr.md)|Fusionne deux séquences contrôlées ordonnées.|  
|[list::pop\_back](../dotnet/list-pop-back-stl-clr.md)|Supprime le dernier élément.|  
|[list::pop\_front](../dotnet/list-pop-front-stl-clr.md)|Supprime le premier élément.|  
|[list::push\_back](../dotnet/list-push-back-stl-clr.md)|Ajoute un nouveau dernier élément.|  
|[list::push\_front](../dotnet/list-push-front-stl-clr.md)|Ajoute d'un nouveau d'élément.|  
|[list::rbegin](../dotnet/list-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[list::remove](../dotnet/list-remove-stl-clr.md)|Supprime un élément avec la valeur spécifiée.|  
|[list::remove\_if](../dotnet/list-remove-if-stl-clr.md)|Supprime les éléments qui réussissent un test spécifique.|  
|[list::rend](../dotnet/list-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[list::resize](../dotnet/list-resize-stl-clr.md)|Change le nombre d'éléments.|  
|[list::reverse](../dotnet/list-reverse-stl-clr.md)|Renverse la séquence contrôlée.|  
|[list::size](../dotnet/list-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[list::sort](../dotnet/list-sort-stl-clr.md)|Ordonne la séquence contrôlée.|  
|[list::splice](../dotnet/list-splice-stl-clr.md)|Liens de Restitches entre les nœuds.|  
|[list::swap](../dotnet/list-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[list::to\_array](../dotnet/list-to-array-stl-clr.md)|Copie la séquence contrôlée dans un nouveau tableau.|  
|[list::unique](../dotnet/list-unique-stl-clr.md)|Supprime les éléments adjacents qui réussissent un test spécifié.|  
  
|Propriété|Description|  
|---------------|-----------------|  
|[list::back\_item](../dotnet/list-back-item-stl-clr.md)|Accède au dernier élément.|  
|[list::front\_item](../dotnet/list-front-item-stl-clr.md)|Accède au premier élément.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[list::operator\=](../dotnet/list-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)|Détermine si un objet de `list` n'est pas égal à un autre objet de `list`.|  
|[operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)|Détermine si un objet de `list` est inférieur à un autre objet de `list`.|  
|[operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Détermine si un objet de `list` est inférieur ou égal à un objet de `list`.|  
|[operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)|Détermine si un objet de `list` n'est pas égal à un autre objet de `list`.|  
|[operator\> \(list\)](../dotnet/operator-greater-than-list-stl-clr.md)|Détermine si un objet de `list` est plus grand qu'un autre objet de `list`.|  
|[operator\>\= \(list\)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Détermine si un objet de `list` est supérieur ou égal à un objet de `list`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Parcourir les éléments.|  
|<xref:System.Collections.ICollection>|Maintenir le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Parcourir les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintenir le groupe d'éléments typés.|  
|IList\<Value\>|Maintenir le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle comme des nœuds individuels dans une liste de liens bidirectionnelle.  Cela réorganise les éléments en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans déranger les éléments restants.  Par conséquent, une liste est un bon candidat de conteneur sous\-jacent de la classe de modèle [queue](../dotnet/queue-stl-clr.md) ou la classe de modèle [pile](../dotnet/stack-stl-clr.md).  
  
 Un objet `list` prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer aux éléments adjacents à partir d'un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [list::end](../dotnet/list-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, s'il est présent.  Vous pouvez incrémenter un itérateur de liste pour atteindre le nœud principal, et il est alors égal à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à une liste directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  Une liste n'est donc `not` utilisable comme conteneur sous\-jacent de la classe de modèle [priority\_queue](../dotnet/priority-queue-stl-clr.md).  
  
 Un itérateur de liste contient un descripteur vers son nœud associé à la liste, qui lui même contient un descripteur vers son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur de liste reste valide à condition que le nœud associé dans la liste soit associé à une certaine liste.  De plus, un itérateur valide est déréférencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur de l'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne détruit pas \(`not`\) ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/list\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [deque](../dotnet/deque-stl-clr.md)   
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [queue](../dotnet/queue-stl-clr.md)   
 [pile](../dotnet/stack-stl-clr.md)   
 [vecteur](../dotnet/vector-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)