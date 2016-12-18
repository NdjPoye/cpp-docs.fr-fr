---
title: "multiset (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/set> (STL/CLR)"
  - "en-tête <set> (STL/CLR)"
  - "multiset (classe) (STL/CLR)"
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet qui contrôle une séquence de longueur variable d'éléments ayant un accès bidirectionnel.  Vous utilisez le conteneur `multiset` pour gérer une séquence d'éléments en tant qu'arbre \(presque\) équilibré de noeuds, chacun stockant un élément.  
  
 Dans la description ci\-dessous, `GValue` est le même que `GKey`, qui est à son tour identique à `Key` sauf si ce dernier est un type de référence, auquel cas il s'agit `Key^`.  
  
## Syntaxe  
  
```  
template<typename Key>  
    ref class multiset  
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
|[multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[multiset::const\_reference](../dotnet/multiset-const-reference-stl-clr.md)|Type d'une référence constante à un élément.|  
|[multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|Le type d'un itérateur inverse constant pour la séquence contrôlée.|  
|[multiset::difference\_type](../dotnet/multiset-difference-type-stl-clr.md)|Le type d'une distance \(possiblement signée\) entre deux éléments.|  
|[multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)|Le type de l'interface générique pour le conteneur.|  
|[multiset::generic\_iterator](../dotnet/multiset-generic-iterator-stl-clr.md)|Le type d'un itérateur pour l'interface générique pour le conteneur.|  
|[multiset::generic\_reverse\_iterator](../dotnet/multiset-generic-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour l'interface générique pour le conteneur.|  
|[multiset::generic\_value](../dotnet/multiset-generic-value-stl-clr.md)|Le type d'un élément pour l'interface générique pour le conteneur.|  
|[multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)|Type d'un itérateur pour la séquence contrôlée.|  
|[multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)|Le classement délégue pour deux clés.|  
|[multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)|Type d'une clé de classement.|  
|[multiset::reference](../dotnet/multiset-reference-stl-clr.md)|Type d'une référence à un élément.|  
|[multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)|Le type d'un itérateur inversé pour la séquence contrôlée.|  
|[multiset::size\_type](../dotnet/multiset-size-type-stl-clr.md)|Le type d'une distance \(non\-négative\) entre deux éléments.|  
|[multiset::value\_compare](../dotnet/multiset-value-compare-stl-clr.md)|Le classement délégué pour deux valeurs d'élements.|  
|[multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)|Le type d'un élément.|  
  
|Méthode|Description|  
|-------------|-----------------|  
|[multiset::begin](../dotnet/multiset-begin-stl-clr.md)|Désigne le début de la séquence contrôlée.|  
|[multiset::clear](../dotnet/multiset-clear-stl-clr.md)|Supprime tous les éléments.|  
|[multiset::count](../dotnet/multiset-count-stl-clr.md)|Compte les éléments qui correspondent à une clé spécifiée.|  
|[multiset::empty](../dotnet/multiset-empty-stl-clr.md)|Teste si aucun élément n'est présent.|  
|[multiset::end](../dotnet/multiset-end-stl-clr.md)|Désigne la fin de la séquence contrôlée.|  
|[multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)|Recherche la plage qui correspond à une clé spécifiée.|  
|[multiset::erase](../dotnet/multiset-erase-stl-clr.md)|Supprime les éléments placés aux positions spécifiées.|  
|[multiset::find](../dotnet/multiset-find-stl-clr.md)|Recherche un élément qui correspond à une clé spécifiée.|  
|[multiset::insert](../dotnet/multiset-insert-stl-clr.md)|Ajoute les éléments.|  
|[multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)|Copie le délégué de commande pour deux clés.|  
|[multiset::lower\_bound](../dotnet/multiset-lower-bound-stl-clr.md)|Recherche le début de la plage qui correspond à une clé spécifiée.|  
|[multiset::make\_value](../dotnet/multiset-make-value-stl-clr.md)|Construit un objet doté d'une valeur.|  
|[multiset::multiset](../dotnet/multiset-multiset-stl-clr.md)|Construit un objet container.|  
|[multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)|Désigne le début de la séquence contrôlée inversée.|  
|[multiset::rend](../dotnet/multiset-rend-stl-clr.md)|Désigne la fin de la séquence contrôlée inversée.|  
|[multiset::size](../dotnet/multiset-size-stl-clr.md)|Compte le nombre d'éléments.|  
|[multiset::swap](../dotnet/multiset-swap-stl-clr.md)|Échange le contenu de deux conteneurs.|  
|[multiset::to\_array](../dotnet/multiset-to-array-stl-clr.md)|Copie la séquence contrôlée dans un tableau.|  
|[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)|Recherche la fin de la plage qui correspond à une clé spécifiée.|  
|[multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)|Copie le classement délégué pour deux valeurs d'éléments.|  
  
|Opérateur|Description|  
|---------------|-----------------|  
|[multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)|Remplace la séquence contrôlée.|  
|[operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)|Détermine si un objet de `multiset` n'est pas égal à un autre objet de `multiset`.|  
|[operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)|Détermine si un objet de `multiset` est inférieur à un autre objet de `multiset`.|  
|[operator\<\= \(multiset\)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)|Détermine si un objet de `multiset` est inférieur ou égal à un objet de `multiset`.|  
|[operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)|Détermine si un objet de `multiset` n'est pas égal à un autre objet de `multiset`.|  
|[operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)|Détermine si un objet de `multiset` est plus grand qu'un autre objet de `multiset`.|  
|[operator\>\= \(multiset\)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)|Détermine si un objet de `multiset` est supérieur ou égal à un objet de `multiset`.|  
  
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
  
 L'objet classifie la séquence qu'il contrôle en appelant un objet délégué stocké de type [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md).  Vous pouvez spécifier l'objet délégué stocké lorsque vous construisez le multiset; si vous ne spécifiez aucun objet délégué, la valeur par défaut est la comparaison `operator<(key_type, key_type)`.  Vous accédez à cet objet stocké en appelant la méthode [multiset::key\_comp](../dotnet/multiset-key-comp-stl-clr.md)`()`.  
  
 Cet objet délégué doit appliquer un ordre strict faible sur les clés du type [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md).  Cela signifie, pour deux clés quelconques `X` et `Y`:  
  
 `key_comp()(X, Y)` retourne le même résultat booléen à chaque appel.  
  
 Si `key_comp()(X, Y)` est true, alors `key_comp()(Y, X)` doit être false.  
  
 Si `key_comp()(X, Y)` est true, alors `X` devient donc classé avant `Y`.  
  
 Si `!key_comp()(X, Y) && !key_comp()(Y, X)` est vrai, alors `X` et `Y` ont un classement équivalent.  
  
 Pour tout élément `X` qui précède `Y` dans la séquence contrôlée, `key_comp()(Y, X)` est false. \(Pour l'objet délégué par défaut, les clés ne perdent jamais en valeur.\) Contrairement à la classe de modèle [set](../dotnet/set-stl-clr.md), un objet de classe de modèle `multiset` n'a pas forcément besoin que les clés pour les éléments soient uniques. \(Deux clés ou plus peuvent être classées de manière équivalente.\)  
  
 Chaque élément sert de clé et de valeur.  La séquence est représentée d'une manière qui autorise la recherche, l'insertion, et la suppression d'un élément aléatoire avec un nombre d'opérations proportionnel au logarithme du nombre d'éléments dans la séquence \(complexité logarithmique\).  De plus, insérer un élément n'invalide aucun itérateur, et la suppression d'un élément invalide uniquement les itérateurs pointant vers l'élément supprimé.  
  
 Un multiset prend en charge les itérateurs bidirectionnels, ce qui signifie que vous pouvez passer aux éléments adjacents à partir d'un itérateur qui indique un élément dans la séquence contrôlée.  Un nœud principal spécial correspond à l'itérateur retourné par [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`.  Vous pouvez décrémenter l'itérateur pour atteindre le dernier élément de la séquence contrôlée, s'il est présent.  Vous pouvez incrémenter un itérateur de multiset pour atteindre le nœud principal, et il est alors égal à `end()`.  Mais vous ne pouvez pas déréférencer l'itérateur retourné par `end()`.  
  
 Notez que vous ne pouvez pas faire référence à un multiset directement avec sa position numérique \-\- cela requiert un itérateur à accès aléatoire.  
  
 Un itérateur de multiset contient un descripteur vers son nœud associé au multiset, qui lui même contient un descripteur vers son conteneur associé.  Vous pouvez utiliser les itérateurs uniquement avec leurs objets conteneurs associés.  Un itérateur de multiset reste valide à condition que son nœud de multiset associé soit associé à un multiset.  De plus, un itérateur valide est déréférencable \-\- vous pouvez l'utiliser pour accéder et modifier la valeur de l'élément qu'il indique \-\- sous réserve qu'il ne soit pas égal à `end()`.  
  
 Effacer ou supprimer un élément appelle le destructeur pour sa valeur stockée.  Détruire le conteneur efface tous les éléments.  Par conséquent, un conteneur dont le type d'élément est une classe de base garantit qu'aucun élément ne survive au conteneur.  Notez, toutefois, qu'un conteneur de descripteurs ne détruit pas \(`not`\) ses éléments.  
  
## Configuration requise  
 **En\-tête :** \<cliext\/set\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [set](../dotnet/set-stl-clr.md)   
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)