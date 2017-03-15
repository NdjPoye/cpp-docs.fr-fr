---
title: "hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/hash_set> [STL/CLR]"
  - "en-tête <hash_set> [STL/CLR]"
  - "classe hash_set [STL/CLR]"
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `hash_set` pour gérer une séquence d'éléments comme une table de hachage, chaque entrée de table enregistrant une liste liée bidirectionnelle de nœuds, et chaque nœud stockant un élément.  La valeur de chaque élément est utilisée comme clé, pour classer la séquence.  
  
 Dans la description ci\-dessous, `GValue` est le même que `GKey`, qui est à son tour identique à `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit `Key^`.  
  
## Syntaxe  
  
```  
template<typename Key>  
    ref class hash_set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### Paramètres  
 Clé  
 Type du composant clé d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[hash\_set::const\_iterator](../dotnet/hash-set-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[hash\_set::const\_reference](../dotnet/hash-set-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[hash\_set::const\_reverse\_iterator](../dotnet/hash-set-const-reverse-iterator-stl-clr.md)|Type d'un itérateur inverse constant pour la séquence contrôlée..|  
|[hash\_set::difference\_type](../dotnet/hash-set-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[hash\_set::generic\_container](../dotnet/hash-set-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[hash\_set::generic\_iterator](../dotnet/hash-set-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[hash\_set::generic\_reverse\_iterator](../dotnet/hash-set-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[hash\_set::generic\_value](../dotnet/hash-set-generic-value-stl-clr.md)|Le type d'un élément pour une utilisation avec l'interface générique pour le conteneur.|  
|[hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md)|Le délégué de hachage pour une clé.|  
|[hash\_set::iterator](../dotnet/hash-set-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md)|Le classement délègue pour deux clés.|  
|[hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[hash\_set::reference](../dotnet/hash-set-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[hash\_set::reverse\_iterator](../dotnet/hash-set-reverse-iterator-stl-clr.md)|Type d'un itérateur inversé pour la séquence contrôlée.|  
|[hash\_set::size\_type](../dotnet/hash-set-size-type-stl-clr.md)|Type d'une \(non\-negative\) distance entre deux éléments.|  
|[hash\_set::value\_compare](../dotnet/hash-set-value-compare-stl-clr.md)|Le classement délègue pour deux valeurs d'éléments.|  
|[hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonctions membres|Description|  
|-----------------------|-----------------|  
|[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[hash\_set::bucket\_count](../dotnet/hash-set-bucket-count-stl-clr.md)|Compte le nombre de buckets.|  
|[hash\_set::clear](../dotnet/hash-set-clear-stl-clr.md)|Supprime tous les éléments.|  
|[hash\_set::count](../dotnet/hash-set-count-stl-clr.md)|Compte les éléments qui correspondent à la clé spécifiée.|  
|[hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[hash\_set::erase](../dotnet/hash-set-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[hash\_set::find](../dotnet/hash-set-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)|Copie le délégué de hachage pour une clé.|  
|[hash\_set::hash\_set](../dotnet/hash-set-hash-set-stl-clr.md)|Construit un objet container.|  
|[hash\_set::insert](../dotnet/hash-set-insert-stl-clr.md)|Ajoute les éléments.|  
|[hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)|Copie le délégué de classement pour deux clés.|  
|[hash\_set::load\_factor](../dotnet/hash-set-load-factor-stl-clr.md)|Compte les éléments moyens par compartiment.|  
|[hash\_set::lower\_bound](../dotnet/hash-set-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[hash\_set::make\_value](../dotnet/hash-set-make-value-stl-clr.md)|Construit un objet valeur.|  
|[hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md)|Obtient ou définit les éléments de chaque compartiment.|  
|[hash\_set::rbegin](../dotnet/hash-set-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md)|Régénère la table de hachage.|  
|[hash\_set::rend](../dotnet/hash-set-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[hash\_set::size](../dotnet/hash-set-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[hash\_set::swap](../dotnet/hash-set-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[hash\_set::to\_array](../dotnet/hash-set-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
|[hash\_set::upper\_bound](../dotnet/hash-set-upper-bound-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[hash\_set::value\_comp](../dotnet/hash-set-value-comp-stl-clr.md)|Copie le délégué de classement pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Séquence à travers les éléments.|  
|<xref:System.Collections.ICollection>|Contient le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Séquence dans les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Contient le groupe d'éléments typés.|  
|IHashKey\<, valeur\>|Contient le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle comme des nœuds dans une liste liée bidirectionnelle.  Pour accélérer l'accès, l'objet contient également un tableau de longueur variée de pointeurs dans la liste \(table de hachage\), la gestion et la liste entière comme séquence de sous\-listes, ou compartiments.  Il insère des éléments dans un compartiment qu'il garde trié en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans éléments restants inquiétants.  
  
 L'objet classifie chaque compartiment qu'il contrôle en appelant un objet délégué stockées de type [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stockée lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<=(key_type, key_type)`.  
  
 Vous accédez à l'objet délégué stocké en appelant la fonction membre [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Ce objet délégué doit définir le classement équivalent entre les clés du type [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen sur chaque appel.  
  
 Si `key_comp()(X, Y) && key_comp()(Y, X)` est true, alors `X` et `Y` ont un classement équivalent.  
  
 Toute règle de tri qui se comporte comme `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` ou `operator==(key_type, key_type)` définit l'ordre équivalent.  
  
 Notez que le conteneur ne garantit que les éléments dont les clés ont un classement équivalent \(et qui hachent à la même valeur entière\) et qui sont adjacents dans un compartiment.  Contrairement à la classe de modèle [hash\_multiset](../dotnet/hash-multiset-stl-clr.md), un objet de classe de modèle `hash_set` garantit que les clés pour les éléments sont uniques. \(Deux clés n'ont pas un classement équivalent.\)  
  
 L'objet détermine quel compartiment doit contenir une clé de tri donnée en appelant un objet délégué stockées de type [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  Vous accédez à cet objet stocké en appelant la fonction membre [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` pour obtenir une valeur entière qui dépend de la valeur de clé.  Vous pouvez spécifier l'objet délégué stockée lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la fonction `System::Object::hash_value(key_type)`.  Cela signifie, pour des clés quelconques `X` et `Y`:  
  
 `hash_delegate()(X)` retourne le même entier sur chaque appel.  
  
 Si `X` et `Y` ont un classement équivalent, alors `hash_delegate()(X)` doit retourner le même résultat entier que `hash_delegate()(Y)`.  
  
 Chaque élément sert de clé\/valeur.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément aléatoire avec un nombre d'opérations qui dépend du nombre d'éléments dans la séquence \(à temps fixe\) \-\- au moins dans l'idéal.  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs correspondant au point de l'élément supprimé.  
  
 Si les valeurs hachées ne sont pas distribuées uniformément ; toutefois, une table de hachage peut se dégénérer.  Dans le cas extrême \-\- pour une fonction de hachage qui retourne toujours la même valeur \-\- la recherche, l'insertion, la suppression sont proportionnelles au nombre d'éléments dans la séquence \(temps linéaire\).  Le conteneur tente de sélectionner une fonction de hachage raisonnable, la taille moyenne de création de compartiments, et une taille de brouillage \(nombre total de compartiments\), mais vous pouvez remplacer tout ou une partie de ces choix.  Consultez, par exemple, les fonctions [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) et [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Un hash\_set prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez faire passer aux éléments adjacents pour un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, le cas échéant.  Vous pouvez incrémenter un itérateur de hachage pour atteindre le nœud principal, et il compare alors l'égalité avec `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à un élément de hachage directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur de hachage enregistre une gestion de son nœud associé de hachage, qui enregistre ensuite un descripteur de son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneur associés.  Un itérateur de hachage reste valide à condition que son nœud associé de hachage soit associé à un certain ensemble de hachage.  De plus, un itérateur valide est dereferencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur d'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effaçant ou supprimer un élément appelle le destructeur de la valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survit au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne `not` détruit ses éléments.  
  
## Configuration requise  
 **En\-tête:** \<cliext\/hash\_set\>  
  
 **Espace de nom :** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)