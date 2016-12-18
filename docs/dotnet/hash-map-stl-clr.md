---
title: "hash_map (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/hash_map> [STL/CLR]"
  - "en-tête <hash_map> [STL/CLR]"
  - "classe hash_map [STL/CLR]"
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `hash_map` pour gérer une séquence d'éléments comme une table de hachage, chaque entrée de table enregistrant une liste liée bidirectionnelle de nœuds, et chaque nœud stockant un élément.  Un élément se compose d'une clé, pour classer la séquence, et d'une valeur mappée.  
  
 Dans la description ci\-dessous, `GValue` est la même chose que :  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 où :  
  
 `GKey` est la même chose que `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Key^`.  
  
 `GMapped` est la même chose que `Mapped` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Mapped^`.  
  
## Syntaxe  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Clé  
 Type du composant clé d'un élément dans la séquence contrôlée.  
  
 Mappé  
 Type du composant additionnel d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[hash\_map::const\_iterator](../dotnet/hash-map-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[hash\_map::const\_reference](../dotnet/hash-map-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[hash\_map::const\_reverse\_iterator](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|Type d'un itérateur inverse constant pour la séquence contrôlée..|  
|[hash\_map::difference\_type](../dotnet/hash-map-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[hash\_map::generic\_reverse\_iterator](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[hash\_map::generic\_value](../dotnet/hash-map-generic-value-stl-clr.md)|Le type d'un élément pour une utilisation avec l'interface générique pour le conteneur.|  
|[hash\_map::hasher](../dotnet/hash-map-hasher-stl-clr.md)|Le hachage délègue pour une clé.|  
|[hash\_map::iterator](../dotnet/hash-map-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[hash\_map::key\_compare](../dotnet/hash-map-key-compare-stl-clr.md)|Le classement délégué pour deux clés.|  
|[hash\_map::key\_type](../dotnet/hash-map-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[hash\_map::mapped\_type](../dotnet/hash-map-mapped-type-stl-clr.md)|Type de la valeur mappée associée à chaque clé.|  
|[hash\_map::reference](../dotnet/hash-map-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[hash\_map::reverse\_iterator](../dotnet/hash-map-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[hash\_map::size\_type](../dotnet/hash-map-size-type-stl-clr.md)|Type d'une \(non\-negative\) distance entre deux éléments.|  
|[hash\_map::value\_compare](../dotnet/hash-map-value-compare-stl-clr.md)|Le classement délégué pour deux valeurs d'éléments.|  
|[hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonctions membres|Description|  
|-----------------------|-----------------|  
|[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)|Compte le nombre de buckets.|  
|[hash\_map::clear](../dotnet/hash-map-clear-stl-clr.md)|Supprime tous les éléments.|  
|[hash\_map::count](../dotnet/hash-map-count-stl-clr.md)|Compte les éléments qui correspondent à la clé spécifiée.|  
|[hash\_map::empty](../dotnet/hash-map-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[hash\_map::erase](../dotnet/hash-map-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[hash\_map::find](../dotnet/hash-map-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[hash\_map::hash\_delegate](../dotnet/hash-map-hash-delegate-stl-clr.md)|Copie le délégué de hachage pour une clé.|  
|[hash\_map::hash\_map](../dotnet/hash-map-hash-map-stl-clr.md)|Construit un objet container.|  
|[hash\_map::insert](../dotnet/hash-map-insert-stl-clr.md)|Ajoute les éléments.|  
|[hash\_map::key\_comp](../dotnet/hash-map-key-comp-stl-clr.md)|Copie le délégué de classement pour deux clés.|  
|[hash\_map::load\_factor](../dotnet/hash-map-load-factor-stl-clr.md)|Compte le nombre moyens d'éléments par compartiment.|  
|[hash\_map::lower\_bound](../dotnet/hash-map-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[hash\_map::make\_value](../dotnet/hash-map-make-value-stl-clr.md)|Construit un objet de valeur.|  
|[hash\_map::max\_load\_factor](../dotnet/hash-map-max-load-factor-stl-clr.md)|Obtient ou définit les éléments de chaque compartiment.|  
|[hash\_map::rbegin](../dotnet/hash-map-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[hash\_map::rehash](../dotnet/hash-map-rehash-stl-clr.md)|Régénère la table de hachage.|  
|[hash\_map::rend](../dotnet/hash-map-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[hash\_map::size](../dotnet/hash-map-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[hash\_map::swap](../dotnet/hash-map-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[hash\_map::to\_array](../dotnet/hash-map-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
|[hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)|Recherche la fin de la plage qui correspond à une clé spécifiée.|  
|[hash\_map::value\_comp](../dotnet/hash-map-value-comp-stl-clr.md)|Copie le délégué de classement pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[hash\_map::operator\=](../dotnet/hash-map-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[hash\_map::operator](../dotnet/hash-map-operator-stl-clr.md)|Mappe une clé à sa valeur mappée associée.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Séquence à travers les éléments.|  
|<xref:System.Collections.ICollection>|Contient le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Séquence dans les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Contient le groupe d'éléments typés.|  
|<xref:System.Collections.Generic.IDictionary%602>|Garde un groupe de paires {clé,valeur}.|  
|IHashKey\<, valeur\>|Contient le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle comme des nœuds dans une liste liée bidirectionnelle.  Pour accélérer l'accès, l'objet contient également un tableau de longueur variée de pointeurs dans la liste \(table de hachage\), la gestion et la liste entière comme séquence de sous\-listes, ou compartiments.  Il insère des éléments dans un compartiment qu'il garde trié en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans éléments restants inquiétants.  
  
 L'objet classifie chaque compartiment qu'il contrôle en appelant un objet délégué stockées de type [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stockée lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<=(key_type, key_type)`.  
  
 Vous accédez à l'objet délégué stocké en appelant la fonction membre [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Ce objet délégué doit définir le classement équivalent entre les clés du type [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen sur chaque appel.  
  
 Si `key_comp()(X, Y) && key_comp()(Y, X)` est true, alors `X` et `Y` ont un classement équivalent.  
  
 Toute règle de tri qui se comporte comme `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` ou `operator==(key_type, key_type)` définit l'ordre équivalent.  
  
 Notez que le conteneur ne garantit que les éléments dont les clés ont un classement équivalent \(et qui hachent à la même valeur entière\) et qui sont adjacents dans un compartiment.  Contrairement à la classe de modèle [hash\_multimap](../dotnet/hash-multimap-stl-clr.md), un objet de classe de modèle `hash_map` garantit que les clés pour les éléments sont uniques. \(Deux clés n'ont pas un classement équivalent.\)  
  
 L'objet détermine quel compartiment doit contenir une clé de tri donnée en appelant un objet délégué stockées de type [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  Vous accédez à cet objet stocké en appelant la fonction membre [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` pour obtenir une valeur entière qui dépend de la valeur de clé.  Vous pouvez spécifier l'objet délégué stockée lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la fonction `System::Object::hash_value(key_type)`.  Cela signifie, pour des clés quelconques `X` et `Y`:  
  
 `hash_delegate()(X)` retourne le même entier sur chaque appel.  
  
 Si `X` et `Y` ont un classement équivalent, alors `hash_delegate()(X)` doit retourner le même résultat entier que `hash_delegate()(Y)`.  
  
 Chaque élément contient une clé distincte et une valeur associée.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément aléatoire avec un nombre d'opérations qui dépend du nombre d'éléments dans la séquence \(à temps fixe\) \-\- au moins dans l'idéal.  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs correspondant au point de l'élément supprimé.  
  
 Si les valeurs hachées ne sont pas distribuées uniformément ; toutefois, une table de hachage peut se dégénérer.  Dans le cas extrême \-\- pour une fonction de hachage qui retourne toujours la même valeur \-\- la recherche, l'insertion, la suppression sont proportionnelles au nombre d'éléments dans la séquence \(temps linéaire\).  Le conteneur tente de sélectionner une fonction de hachage raisonnable, la taille moyenne de création de compartiments, et une taille de brouillage \(nombre total de compartiments\), mais vous pouvez remplacer tout ou une partie de ces choix.  Consultez, par exemple, les fonctions [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) et [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Un hash\_map prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer aux éléments adjacents à partir d'un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, le cas échéant.  Vous pouvez incrémenter un itérateur de hash\_map pour atteindre le nœud principal, et il est alors égal à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à un hash\_map directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur de hash\_map contient une handle vers son nœud hash\_map associé, qui elle\-même contient une handle vers son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur de hash\_map reste valide à condition que son nœud de hash\_map associé soit associé à un certain hash\_map.  De plus, un itérateur valide est dereferencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur d'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effaçant ou supprimer un élément appelle le destructeur de la valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survit au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs `not` détruit ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)