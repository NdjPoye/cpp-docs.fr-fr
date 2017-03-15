---
title: hash_compare, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/stdext::hash_compare
- std.hash_compare
- hash_compare
- std::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: e493529a2511d92b9c99f820bd05b8f911ef9280
ms.lasthandoff: 02/24/2017

---
# <a name="hashcompare-class"></a>hash_compare, classe
La classe de modèle décrit un objet qui peut être utilisé par les conteneurs associatifs de hachage, hash_map, hash_multimap, hash_set ou hash_multiset, comme objet de paramètre **Traits** par défaut pour ordonner et hacher les éléments qu’ils contiennent.  
  
## <a name="syntax"></a>Syntaxe  
  
class hash_compare { Traits comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare(Traits pred); size_t operator()(const Key& key) const; bool operator()( const Key& key1, const Key& key2) const; };  
  
## <a name="remarks"></a>Notes  
 Chaque conteneur associatif de hachage stocke un objet de caractéristiques de hachage de type **Traits** (un paramètre de modèle). Vous pouvez dériver une classe d’une spécialisation de hash_compare pour remplacer de manière sélective certaines fonctions et certains objets, ou vous pouvez fournir votre propre version de cette classe si vous répondez à certaines exigences minimales. En particulier, pour un objet hash_comp de type **hash_compare\<Key, Traits>**, le comportement suivant est requis par les conteneurs ci-dessus :  
  
-   Pour toutes les valeurs `key` de type **Key**, l’appel **hash_comp**( `key`) sert de fonction de hachage, ce qui produit une distribution des valeurs de **type size_t**. La fonction fournie par hash_compare retourne `key`.  
  
-   Pour toutes les valeurs `key1` de type **Key** précédant `key2` dans la séquence et ayant la même valeur de hachage (la valeur retournée par la fonction de hachage), **hash_comp**( `key2`, `key1`) a la valeur false. La fonction doit imposer un ordonnancement total sur les valeurs de type **Key**. La fonction fournie par hash_compare retourne *comp*( `key2`, `key1`) `,` où *comp* est un objet stocké de type **Traits** que vous pouvez spécifier lors de la construction de l’objet hash_comp. Pour le type de paramètre **Traits** **less\<Key>**, la valeur des clés de tri ne va jamais en diminuant.  
  
-   La constante entière **bucket_size** spécifie le nombre moyen d’éléments par « compartiment » (entrée de table de hachage) que le conteneur doit essayer de ne pas dépasser. La valeur doit être supérieure à zéro. La valeur fournie par hash_compare est 4.  
  
-   La constante entière **min_buckets** spécifie le nombre minimal de compartiments à conserver dans la table de hachage. Il doit s'agir d'une puissance de deux et sa valeur doit être supérieure à zéro. La valeur fournie par hash_compare est 8.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [stdext, espace de noms](../standard-library/stdext-namespace.md).  
  
## <a name="example"></a>Exemple  
 Consultez les exemples pour [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map__hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap__hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set__hash_set) et [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset__hash_multiset) pour voir comment déclarer et utiliser hash_compare.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<hash_map>  
  
 **Espace de noms :** stdext  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




