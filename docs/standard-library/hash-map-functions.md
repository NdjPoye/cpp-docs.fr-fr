---
title: '&lt;hash_map&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 394a9ffe15c256a43cdf16ffd164f2e907ab0535
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt;, fonctions
|||  
|-|-|  
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|  
  
##  <a name="swap_hash_map"></a>  swap (hash_map)  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_map, classe](../standard-library/unordered-map-class.md).  
  
 Échange les éléments de deux hash_maps.  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 hash_map dont les éléments doivent être échangés avec ceux du mappage `left`.  
  
 `left`  
 hash_map dont les éléments doivent être échangés avec ceux du mappage `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur la classe de conteneur hash_map pour exécuter la fonction membre `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*). Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template \<class T> void swap(T&, T&)**, dans le fichier d’en-tête d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [The stdext Namespace (L’espace de noms stdext)](../standard-library/stdext-namespace.md).  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_multimap, classe](../standard-library/unordered-multimap-class.md).  
  
 Échange les éléments de deux hash_multimaps.  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 hash_multimap dont les éléments doivent être échangés avec ceux du mappage `left`.  
  
 `left`  
 hash_multimap dont les éléments doivent être échangés avec ceux du mappage `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur la classe de conteneur hash_multimap pour exécuter la fonction membre `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template \<class T> void swap(T&, T&)**, dans le fichier d’en-tête d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [The stdext Namespace (L’espace de noms stdext)](../standard-library/stdext-namespace.md).  
  
## <a name="see-also"></a>Voir aussi  
 [<hash_map>](../standard-library/hash-map.md)




