---
title: '&lt;vector&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <vector>
- std.<vector>
- std::<vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 77c13a5f8d813bbeaa0dae2307769a575bb22fa8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltvectorgt"></a>&lt;vector&gt;
Définit la classe de modèle de conteneur vector et plusieurs modèles de prise en charge.  
  
 Le conteneur `vector` permet d'organiser les éléments d'un type donné dans une séquence linéaire. Il fournit un accès aléatoire rapide à chaque élément, et gère les ajouts et suppressions dynamiques dans la séquence. Il est recommandé d'utiliser le conteneur `vector` pour une séquence si votre priorité est de garantir des performances optimales au niveau de l'accès aléatoire.  
  
 Pour plus d’informations sur la classe `vector`, consultez [vector, classe](../standard-library/vector-class.md). Pour plus d’informations sur la spécialisation `vector<bool>`, consultez [vector\<bool>, classe](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Paramètres  
 Type  
 Paramètre de modèle pour le type de données stockées dans le vecteur.  
  
 Allocateur  
 Paramètre de modèle pour l'objet allocateur stocké qui gère l'allocation et la libération de mémoire.  
  
 `left`  
 Premier vecteur (à gauche) dans une opération de comparaison.  
  
 `right`  
 Deuxième vecteur (à droite) dans une opération de comparaison.  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator! =](../standard-library/vector-operators.md#op_neq)|Vérifie si le vecteur situé à gauche de l'opérateur n'est pas égal au vecteur situé à droite.|  
|[operator<](../standard-library/vector-operators.md#op_lt)|Vérifie si le vecteur situé à gauche de l'opérateur est inférieur au vecteur situé à droite.|  
|[operator\<=](../standard-library/vector-operators.md#op_gt_eq)|Vérifie si le vecteur situé à gauche de l'opérateur est inférieur ou égal au vecteur situé à droite.|  
|[operator==](../standard-library/vector-operators.md#op_eq_eq)|Vérifie si le vecteur situé à gauche de l'opérateur est égal au vecteur situé à droite.|  
|[operator>](../standard-library/vector-operators.md#op_gt)|Vérifie si le vecteur situé à gauche de l'opérateur est supérieur au vecteur situé à droite.|  
|[operator>=](../standard-library/vector-operators.md#op_gt_eq)|Vérifie si le vecteur situé à gauche de l'opérateur est supérieur ou égal au vecteur situé à droite.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[vector, classe](../standard-library/vector-class.md)|Classe de modèle de conteneurs de séquence qui organisent les éléments d'un type donné dans une disposition linéaire et fournissent un accès aléatoire rapide à chaque élément.|  
  
### <a name="specializations"></a>Spécialisations  
  
|||  
|-|-|  
|[vector\<bool>, classe](../standard-library/vector-bool-class.md)|Spécialisation complète de la classe de modèle vector pour les éléments de type `bool` possédant un allocateur pour le type sous-jacent utilisé par la spécialisation.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<vector>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)


