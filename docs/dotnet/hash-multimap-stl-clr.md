---
title: "hash_multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/hash_map> [STL/CLR]"
  - "en-tête <hash_map> [STL/CLR]"
  - "classe hash_multimap [STL/CLR]"
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle la séquence de longueur variée d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `hash_multimap` pour gérer une séquence d'éléments comme une table de hachage, chaque entrée de table enregistrant une liste liée bidirectionnelle de nœuds, et chaque nœud stockant un élément.  Un élément se compose d'une clé, pour classer la séquence, et d'une valeur mappée.  
  
 Dans la description ci\-dessous, `GValue` est la même chose que :  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 où :  
  
 `GKey` est la même chose que `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Key^`.  
  
 `GMapped` est la même chose que `Mapped` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Mapped^`.  
  
## Syntaxe  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_multimap  
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
  
 Mappé  
 Le type du composant additionnel d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[hash\_multimap::const\_reference](../dotnet/hash-multimap-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[hash\_multimap::const\_reverse\_iterator](../dotnet/hash-multimap-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[hash\_multimap::difference\_type](../dotnet/hash-multimap-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[hash\_multimap::generic\_container](../dotnet/hash-multimap-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[hash\_multimap::generic\_iterator](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[hash\_multimap::generic\_reverse\_iterator](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[hash\_multimap::generic\_value](../dotnet/hash-multimap-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[hash\_multimap::hasher](../dotnet/hash-multimap-hasher-stl-clr.md)|Le hachage délègue pour une clé.|  
|[hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)|Le délégué declassement pour deux clés.|  
|[hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[hash\_multimap::mapped\_type](../dotnet/hash-multimap-mapped-type-stl-clr.md)|Le type de la valeur mappée associée à chaque clé.|  
|[hash\_multimap::reference](../dotnet/hash-multimap-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[hash\_multimap::reverse\_iterator](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[hash\_multimap::size\_type](../dotnet/hash-multimap-size-type-stl-clr.md)|Le type d'une distance \(non\-négative\) entre deux éléments.|  
|[hash\_multimap::value\_compare](../dotnet/hash-multimap-value-compare-stl-clr.md)|Le délégue de classement pour deux valeurs d'éléments.|  
|[hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Fonction membre|Description|  
|---------------------|-----------------|  
|[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[hash\_multimap::bucket\_count](../dotnet/hash-multimap-bucket-count-stl-clr.md)|Compte le nombre de compartiments.|  
|[hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)|Supprime tous les éléments.|  
|[hash\_multimap::count](../dotnet/hash-multimap-count-stl-clr.md)|Compte les éléments qui correspondent à une clé spécifiée.|  
|[hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[hash\_multimap::erase](../dotnet/hash-multimap-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[hash\_multimap::find](../dotnet/hash-multimap-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[hash\_multimap::hash\_delegate](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|Copie le hachage délégué pour une clé.|  
|[hash\_multimap::hash\_multimap](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|Construit un objet container.|  
|[hash\_multimap::insert](../dotnet/hash-multimap-insert-stl-clr.md)|Ajoute les éléments.|  
|[hash\_multimap::key\_comp](../dotnet/hash-multimap-key-comp-stl-clr.md)|Copie le classement délégué pour deux clés.|  
|[hash\_multimap::load\_factor](../dotnet/hash-multimap-load-factor-stl-clr.md)|Compte le nombre moyens d'éléments par compartiment.|  
|[hash\_multimap::lower\_bound](../dotnet/hash-multimap-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[hash\_multimap::make\_value](../dotnet/hash-multimap-make-value-stl-clr.md)|Construit un objet doté d'une valeur.|  
|[hash\_multimap::max\_load\_factor](../dotnet/hash-multimap-max-load-factor-stl-clr.md)|Obtient ou définit les éléments maximum de chaque compartiment.|  
|[hash\_multimap::rbegin](../dotnet/hash-multimap-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[hash\_multimap::rehash](../dotnet/hash-multimap-rehash-stl-clr.md)|Régénère la table de hachage.|  
|[hash\_multimap::rend](../dotnet/hash-multimap-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[hash\_multimap::size](../dotnet/hash-multimap-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[hash\_multimap::swap](../dotnet/hash-multimap-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[hash\_multimap::to\_array](../dotnet/hash-multimap-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
|[hash\_multimap::upper\_bound](../dotnet/hash-multimap-upper-bound-stl-clr.md)|Recherche la fin de la plage qui correspond à une clé spécifiée.|  
|[hash\_multimap::value\_comp](../dotnet/hash-multimap-value-comp-stl-clr.md)|Copie le classement délégué pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Séquence à travers les éléments.|  
|<xref:System.Collections.ICollection>|Contient le groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Séquence à travers les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Contient le groupe d'éléments typés.|  
|IHashKey\<, valeur\>|Contient le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle comme des nœuds individuels dans une liste liée bidirectionnelle.  Pour accélérer l'accès, l'objet contient également un tableau de longueur variée de pointeurs dans la liste \(table de hachage\), gérant la liste entière comme séquence de sous\-listes, ou compartiments.  Il insère des éléments dans un compartiment qu'il garde trié en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans éléments restants gênants.  
  
 L'objet classifie chaque compartiment qu'il contrôle en appelant un objet délégué stockés de type [hash\_set::key\_compare](../dotnet/hash-set-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stockée lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<=(key_type, key_type)`.  
  
 Vous accédez à l'objet délégué stocké en appelant la fonction membre [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Cet objet délégué doit définir le classement équivalent entre les clés du type [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen à chaque appel.  
  
 Si `key_comp()(X, Y) && key_comp()(Y, X)` est vrai, alors `X` et `Y` ont un classement équivalent.  
  
 Toute règle de tri qui se comporte comme `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` ou `operator==(key_type, key_type)` définit l'ordre équivalent.  
  
 Notez que le conteneur ne garantit que les éléments dont les clés ont un classement équivalent \(et qui hachent à la même valeur entière\) et qui sont adjacents dans un compartiment.  Contrairement à la classe de modèle [hash\_map](../dotnet/hash-map-stl-clr.md), un objet de classe de modèle `hash_multimap` n'a pas forcément besoin que les clés pour les éléments soient uniques. \(Deux clés ou plus peuvent être classés de manière équivalente.\)  
  
 L'objet détermine quel compartiment doit contenir une clé de tri donnée en appelant un objet délégué stocké de type [hash\_set::hasher](../dotnet/hash-set-hasher-stl-clr.md).  Vous accédez à cet objet stocké en appelant la fonction membre [hash\_set::hash\_delegate](../dotnet/hash-set-hash-delegate-stl-clr.md)`()` pour obtenir une valeur entière qui dépend de la valeur de clé.  Vous pouvez spécifier l'objet délégué stocké lorsque vous construisez le hash\_set ; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la fonction `System::Object::hash_value(key_type)`.  Cela signifie, pour des clés quelconques `X` et `Y`:  
  
 `hash_delegate()(X)` retourne le même résultat entier à chaque appel.  
  
 Si `X` et `Y` ont un classement équivalent, alors `hash_delegate()(X)` doit retourner le même résultat entier que `hash_delegate()(Y)`.  
  
 Chaque élément contient une clé distincte et une valeur mappée.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément choisi avec un nombre d'opérations qui est indépendant du nombre d'éléments dans la séquence \(à temps fixe\) \-\- au moins dans l'idéal.  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs pointant l'élément supprimé.  
  
 Toutefois, si les valeurs hachées ne sont pas distribuées uniformément, une table de hachage peut se dégénérer.  Dans le cas extrême \-\- pour une fonction de hachage qui retourne toujours la même valeur \-\- la recherche, l'insertion, la suppression sont proportionnelles au nombre d'éléments dans la séquence \(temps linéaire\).  Le conteneur tente de sélectionner une fonction de hachage raisonnable, la taille moyenne de création de compartiments, et une taille de table de hachage \(nombre total de compartiments\), mais vous pouvez remplacer tout ou une partie de ces choix.  Consultez, par exemple, les fonctions [hash\_set::max\_load\_factor](../dotnet/hash-set-max-load-factor-stl-clr.md) et [hash\_set::rehash](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Une multimap de hachage prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer aux éléments adjacents à partir d'un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, s'il est présent.  Vous pouvez incrémenter un itérateur de multimap de hachage pour atteindre le nœud principal, et il est alors égal à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à une multimap de hachage directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur de multimap de hachage contient un descripteur vers son nœud associé à la multimap de hachage, qui elle\-même contient un descripteur vers son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur de multimap de hachage reste valide à condition que son nœud associé à la multimap de hachage soit associé à un certain ensemble de multimap de hachage.  De plus, un itérateur valide est déréférencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur d'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs `not` détruit ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/hash\_map\>  
  
 **Espace de nommage :** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)