---
title: '&lt;hash_set&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: 7
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 2743e67d8077cdf75b51a3dce914ced0894a3392
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt;, fonctions
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_set, classe](../standard-library/unordered-set-class.md).  
  
 Échange les éléments de deux hash_sets.  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 hash_set qui fournit les éléments à échanger ou hash_set dont les éléments doivent être échangés avec ceux du hash_set `left`.  
  
 `left`  
 hash_set dont les éléments doivent être échangés avec ceux du hash_set `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle `swap` est un algorithme spécialisé sur la classe de conteneur hash_set pour exécuter la fonction membre `left``.`[swap](../standard-library/hash-set-class.md#swap)( `right`). Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle  
  
 **template \<class T> void swap(T&, T&),**  
  
 dans l’algorithme de classe fonctionne par assignation et il s’agit d’une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [stdext, espace de noms](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la classe membre [hash_set::swap](../standard-library/hash-set-class.md#swap).  
  
##  <a name="swap_hash_multiset"></a>  swap (hash_multiset)  
  
> [!NOTE]
>  Cette API méthode est obsolète. L’alternative est [unordered_set, classe](../standard-library/unordered-set-class.md).  
  
 Échange les éléments de deux hash_multisets.  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 hash_multiset qui fournit les éléments à échanger ou hash_multiset dont les éléments doivent être échangés avec ceux du hash_multiset `left`.  
  
 `left`  
 hash_multiset dont les éléments doivent être échangés avec ceux du hash_multiset `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle `swap` est un algorithme spécialisé sur la classe de conteneur hash_multiset pour exécuter la fonction membre `left``.`[swap](../standard-library/hash-multiset-class.md#swap)( `right`). Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle  
  
 **template \<class T> void swap(T&, T&),**  
  
 dans l’algorithme de classe fonctionne par assignation et il s’agit d’une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide car elle peut fonctionner avec la représentation interne de la classe conteneur.  
  
 Dans Visual C++ .NET 2003, les membres des fichiers d’en-tête [<hash_map>](../standard-library/hash-map.md) et [<hash_set>](../standard-library/hash-set.md) ne sont plus dans l’espace de noms std. Ils ont été transférés dans l’espace de noms stdext. Pour plus d’informations, consultez [stdext, espace de noms](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la classe membre [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap).  
  
## <a name="see-also"></a>Voir aussi  
 [<hash_set>](../standard-library/hash-set.md)




