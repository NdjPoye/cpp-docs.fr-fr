---
title: "multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/map> (STL/CLR)"
  - "en-tête <map> (STL/CLR)"
  - "multimap (classe) (STL/CLR)"
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contrôle une séquence de longueur variable d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `multimap` pour gérer une séquence d'éléments en tant qu'arbre \(presque\) équilibré de noeuds, chacun stockant un élément.  Un élément se compose d'une clé, pour classer la séquence, et d'une valeur mappée.  
  
 Dans la description ci\-dessous, `GValue` est la même chose que :  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 où :  
  
 `GKey` est la même chose que `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Key^`.  
  
 `GMapped` est la même chose que `Mapped` sauf si ce dernier est un type de référence, auquel cas il s'agit de `Mapped^`.  
  
## Syntaxe  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
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
  
 Mapped  
 Le type du composant additionel d'un élément dans la séquence contrôlée.  
  
## Membres  
  
|Définition de type|Description|  
|------------------------|-----------------|  
|[multimap::const\_iterator](../dotnet/multimap-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[multimap::const\_reference](../dotnet/multimap-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[multimap::const\_reverse\_iterator](../dotnet/multimap-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[multimap::difference\_type](../dotnet/multimap-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[multimap::generic\_iterator](../dotnet/multimap-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[multimap::generic\_reverse\_iterator](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[multimap::generic\_value](../dotnet/multimap-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)|Le classement délégue pour deux clés.|  
|[multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)|Le type de la valeur mappée associée à chaque clé.|  
|[multimap::reference](../dotnet/multimap-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[multimap::reverse\_iterator](../dotnet/multimap-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[multimap::size\_type](../dotnet/multimap-size-type-stl-clr.md)|Le type d'une distance \(non\-négative\) entre deux éléments.|  
|[multimap::value\_compare](../dotnet/multimap-value-compare-stl-clr.md)|Le classement délégué pour deux valeurs d'élements.|  
|[multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Méthode|Description|  
|-------------|-----------------|  
|[multimap::begin](../dotnet/multimap-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[multimap::clear](../dotnet/multimap-clear-stl-clr.md)|Supprime tous les éléments.|  
|[multimap::count](../dotnet/multimap-count-stl-clr.md)|Compte les éléments qui correspondent à une clé spécifiée.|  
|[multimap::empty](../dotnet/multimap-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[multimap::end](../dotnet/multimap-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[multimap::erase](../dotnet/multimap-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[multimap::find](../dotnet/multimap-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[multimap::insert](../dotnet/multimap-insert-stl-clr.md)|Ajoute les éléments.|  
|[multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)|Copie le délégué de commande pour deux clés.|  
|[multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[multimap::make\_value](../dotnet/multimap-make-value-stl-clr.md)|Construit un objet doté d'une valeur.|  
|[multimap::multimap](../dotnet/multimap-multimap-stl-clr.md)|Construit un objet container.|  
|[multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[multimap::rend](../dotnet/multimap-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[multimap::size](../dotnet/multimap-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[multimap::swap](../dotnet/multimap-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[multimap::to\_array](../dotnet/multimap-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
|[multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)|Recherche la fin de la plage qui correspond à une clé spécifiée.|  
|[multimap::value\_comp](../dotnet/multimap-value-comp-stl-clr.md)|Copie le classement délégué pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(multimap\)](../dotnet/operator-inequality-multimap-stl-clr.md)|Détermine si un objet de `multimap` n'est pas égal à un autre objet de `multimap`.|  
|[operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)|Détermine si un objet de `multimap` est inférieur à un autre objet de `multimap`.|  
|[operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|Détermine si un objet de `multimap` est inférieur ou égal à un objet de `multimap`.|  
|[operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)|Détermine si un objet de `multimap` n'est pas égal à un autre objet de `multimap`.|  
|[operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)|Détermine si un objet de `multimap` est plus grand qu'un autre objet de `multimap`.|  
|[operator\>\= \(multimap\)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)|Détermine si un objet de `multimap` est supérieur ou égal à un objet de `multimap`.|  
  
## Interfaces  
  
|Interface|Description|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Dupliquer un objet.|  
|<xref:System.Collections.IEnumerable>|Parcourir les éléments.|  
|<xref:System.Collections.ICollection>|Maintenirle groupe d'éléments.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Parcourir les éléments typés.|  
|<xref:System.Collections.Generic.ICollection%601>|Maintenir le groupe d'éléments typés.|  
|ITree\<Key, Value\>|Maintenir le conteneur générique.|  
  
## Notes  
 L'objet alloue et libère du stockage pour la séquence qu'il contrôle en tant que nœuds individuels.  Il insère des éléments dans un arbre \(presque\) équilibré qu'il garde trié en modifiant les liens entre les nœuds, jamais en copiant le contenu d'un nœud vers un autre.  Cela signifie que vous pouvez insérer et supprimer des éléments librement sans déranger les éléments restants.  
  
 L'objet classifie la séquence qu'il contrôle en appelant un objet délégué stocké de type [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stocké lorsque vous construisez le multimap; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<(key_type, key_type)`.  Vous accédez à cet objet stocké en appelant la méthode [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)`()`.  
  
 Cet objet délégué doit appliquer un ordre strict faible sur les clés du type [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen à chaque appel.  
  
 Si `key_comp()(X, Y)` est true, alors `key_comp()(Y, X)` doit être false.  
  
 Si `key_comp()(X, Y)` est true, alors `X` devient donc classé avant `Y`.  
  
 Si `!key_comp()(X, Y) && !key_comp()(Y, X)` est vrai, alors `X` et `Y` ont un classement équivalent.  
  
 Pour tout élément `X` qui précède `Y` dans la séquence contrôlée, `key_comp()(Y, X)` est false. \(Pour l'objet délégué par défaut, les clés ne perdent jamais en valeur.\) Contrairement à la classe de modèle [map](../dotnet/map-stl-clr.md), un objet de classe de modèle `multimap` n'a pas forcément besoin que les clés pour les éléments soient uniques. \(Deux clés ou plus peuvent être classées de manière équivalente.\)  
  
 Chaque élément contient une clé distincte et une valeur mappée.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément aléatoire avec un nombre d'opérations proportionnel au logarithme du nombre d'éléments dans la séquence \(complexité logarithmique\).  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs pointant vers l'élément supprimé.  
  
 Un multimap prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer aux éléments adjacents à partir d'un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, s'il est présent.  Vous pouvez incrémenter un itérateur de multimap pour atteindre le nœud principal, et il est alors égal à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à une multimap directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur de multimap contient un descripteur vers son nœud associé à la multimap, qui elle\-même contient un descripteur vers son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur de multimap reste valide à condition que son nœud de multimap associé soit associé à un multimap.  De plus, un itérateur valide est déréférencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur de l'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne détruit pas \(`not`\) ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/map\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)