---
title: '&lt;vector&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: e752c3d39787466928b11ff8d644cf9a6558b656
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;, fonctions

  
##  <a name="swap"></a>  swap  
 Échange les éléments de deux vecteurs.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Le vecteur qui fournit les éléments à permuter, ou le vecteur dont les éléments doivent être échangés avec ceux du vecteur `left`.  
  
 `left`  
 Le vecteur dont les éléments doivent être échangés avec ceux du vecteur `right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur le vecteur de classe de conteneur pour exécuter la fonction membre `left`. [vector::swap](../standard-library/vector-class.md) *( right*). Il s’agit d’instances de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [vector::swap](../standard-library/vector-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [\<vector>](../standard-library/vector.md)

