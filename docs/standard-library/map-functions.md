---
title: '&lt;map&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 6
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7972ff0d03f0c7b2378f87c311db633dff2a5d13
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltmapgt-functions"></a>&lt;map&gt;, fonctions
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|  
  
##  <a name="swap_multimap"></a>  swap  (map)
 Échange les éléments de deux classes map.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    map<Key, Traits, Compare, Alloctor>& left,  
    map<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Mappage qui fournit les éléments à échanger ou mappage dont les éléments doivent être échangés avec ceux du mappage `left`.  
  
 `left`  
 Mappage dont les éléments doivent être échangés avec ceux du mappage `right`.  
  
### <a name="remarks"></a>Remarques  
 La fonction de modèle est un algorithme spécialisé sur la carte de la classe conteneur pour exécuter la fonction membre `left`.[ échange](../standard-library/map-class.md#swap)( `right`). Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [map::swap](../standard-library/map-class.md#swap).  
  
##  <a name="swap"></a>  swap  (multimap)
 Échange les éléments de deux multimaps.  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,  
    multimap<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Multimap qui fournit les éléments à échanger ou multimap dont les éléments doivent être échangés avec ceux du multimap `left`.  
  
 `left`  
 Multimap dont les éléments doivent être échangés avec ceux du multimap `right`.  
  
### <a name="remarks"></a>Remarques  
 La fonction de modèle est un algorithme spécialisé sur la carte de classe de conteneur pour s’exécuter sur la classe multimap à la classe conteneur pour exécuter la fonction membre `left`.[ échange](../standard-library/multimap-class.md#swap) ( `right`). Il s’agit d’une instance de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [multimap::swap](../standard-library/multimap-class.md#swap).  
  
## <a name="see-also"></a>Voir aussi  
 [\<map>](../standard-library/map.md)
