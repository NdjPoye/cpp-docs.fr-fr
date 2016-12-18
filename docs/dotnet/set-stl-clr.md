---
title: "set (STL/CLR) | Microsoft Docs"
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
  - "cliext::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/set> (STL/CLR)"
  - "en-tête <set> (STL/CLR)"
  - "set (classe) (STL/CLR)"
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `set` pour gérer une séquence d'éléments en tant qu'arbre \(presque\) équilibré de noeuds, chacun stockant un élément.  
  
 Dans la description ci\-dessous, `GValue` est le même que `GKey`, qui est à son tour identique à `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit `Key^`.  
  
## Syntaxe  
  
```  
template<typename Key>  
    ref class set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Clé  
 Type du composant clé d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[set::const\_iterator](../dotnet/set-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[set::const\_reference](../dotnet/set-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[set::const\_reverse\_iterator](../dotnet/set-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[set::difference\_type](../dotnet/set-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[set::generic\_container](../dotnet/set-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[set::generic\_iterator](../dotnet/set-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[set::generic\_reverse\_iterator](../dotnet/set-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[set::generic\_value](../dotnet/set-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[set::iterator](../dotnet/set-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[set::key\_compare](../dotnet/set-key-compare-stl-clr.md)|Le classement délégue pour deux clés.|  
|[set::key\_type](../dotnet/set-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[set::reference](../dotnet/set-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[set::reverse\_iterator](../dotnet/set-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[set::size\_type](../dotnet/set-size-type-stl-clr.md)|Le type d'une distance \(non\-négative\) entre deux éléments.|  
|[set::value\_compare](../dotnet/set-value-compare-stl-clr.md)|Le classement délégué pour deux valeurs d'élements.|  
|[set::value\_type](../dotnet/set-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[set::begin](../dotnet/set-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[set::clear](../dotnet/set-clear-stl-clr.md)|Supprime tous les éléments.|  
|[set::count](../dotnet/set-count-stl-clr.md)|Compte les éléments qui correspondent à une clé spécifiée.|  
|[set::empty](../dotnet/set-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[set::end](../dotnet/set-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[set::equal\_range](../dotnet/set-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[set::erase](../dotnet/set-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[set::find](../dotnet/set-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[set::insert](../dotnet/set-insert-stl-clr.md)|Ajoute les éléments.|  
|[set::key\_comp](../dotnet/set-key-comp-stl-clr.md)|Copie le délégué de commande pour deux clés.|  
|[set::lower\_bound](../dotnet/set-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[set::make\_value](../dotnet/set-make-value-stl-clr.md)|Construit un objet doté d'une valeur.|  
|[set::rbegin](../dotnet/set-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[set::rend](../dotnet/set-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[set::set](../dotnet/set-set-stl-clr.md)|Construit un objet container.|  
|[set::size](../dotnet/set-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[set::swap](../dotnet/set-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[set::to\_array](../dotnet/set-to-array-stl-clr.md)|Copie la séquence contrôlée dans un nouveau tableau.|  
|[set::upper\_bound](../dotnet/set-upper-bound-stl-clr.md)|Recherche la fin de la plage qui correspond à une clé spécifiée.|  
|[set::value\_comp](../dotnet/set-value-comp-stl-clr.md)|Copie le classement délégué pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[set::operator\=](../dotnet/set-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)|Détermine si un objet de `set` n'est pas égal à un autre objet de `set`.|  
|[operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)|Détermine si un objet de `set` est inférieur à un autre objet de `set`.|  
|[operator\<\= \(set\)](../dotnet/operator-less-or-equal-set-stl-clr.md)|Détermine si un objet de `set` est inférieur ou égal à un objet de `set`.|  
|[operator\=\= \(set\)](../dotnet/operator-equality-set-stl-clr.md)|Détermine si un objet de `set` n'est pas égal à un autre objet de `set`.|  
|[operator\> \(set\)](../dotnet/operator-greater-than-set-stl-clr.md)|Détermine si un objet de `set` est plus grand qu'un autre objet de `set`.|  
|[operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|Détermine si un objet de `set` est supérieur ou égal à un objet de `set`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Parcourir les éléments.|  
|<xref:System.Collections.ICollection>|Maintenir le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Parcourir les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintenir le groupe d'éléments typés.|  
|ITree\<Key, Value\>|Maintenir le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle en tant que nœuds individuels.  Il insère des éléments dans un arbre \(presque\) équilibré qu'il garde trié en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans déranger les éléments restants.  
  
 L'objet classifie la séquence qu'il contrôle en appelant un objet délégué stocké de type [set::key\_compare](../dotnet/set-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stocké lorsque vous construisez l'ensemble ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<(key_type, key_type)`.  Vous accédez à cet objet stocké en appelant la méthode [set::key\_comp](../dotnet/set-key-comp-stl-clr.md)`()`.  
  
 Un objet délégué de la sorte doit imposer un ordre strict faible sur les clés du type [set::key\_type](../dotnet/set-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen à chaque appel.  
  
 Si `key_comp()(X, Y)` est vrai, alors `key_comp()(Y, X)` doit être faux.  
  
 Si `key_comp()(X, Y)` est vrai, alors on dit que `X` commandé avant `Y`.  
  
 Si `!key_comp()(X, Y) && !key_comp()(Y, X)` est vrai, alors `X` et `Y` ont un classement équivalent.  
  
 Pour n'importe quel élément `X` qui précède `Y` dans la séquence contrôlée, `key_comp()(Y, X)` est faux. \(Pour l'objet délégué par défaut, les clés ne perdent jamais en valeur.\) Contrairement à la classe de modèle [set](../dotnet/set-stl-clr.md), un objet de classe de modèle `set` ne requiert pas que les clés pour tous les éléments soient uniques. \(Deux clés ou plus peuvent être classées de manière équivalente.\)  
  
 Chaque élément sert de clé et de valeur.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément aléatoire avec un nombre d'opérations proportionnel au logarithme du nombre d'éléments dans la séquence \(complexité logarithmique\).  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs pointant vers l'élément supprimé.  
  
 Un ensemble prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer à des éléments adjacents donnés un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [set::end](../dotnet/set-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, s'il est présent.  Vous pouvez incrémenter un itérateur d'ensemble pour atteindre le nœud principal, puis il testera son égalité à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire directement référence à un élément d'ensemble avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur d'ensemble stocke un gestionnaire de son nœud d'ensemble, qui lui même stocke un gestionnaire vers son conteneur associé.  Vous pouvez utiliser des itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur d'ensemble reste valide tant que le nœud d'ensemble associé est associé à un certain ensemble.  De plus, un itérateur valide est déréférençable \-\- vous pouvez l'utiliser pour accéder ou modifier la valeur de l'élément qu'il indique \-\- tant qu'il n'est pas égal à `end()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne détruit `not` ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)