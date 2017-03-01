---
title: '&lt;vector&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bb62c0c4e5b2965438539b17ec5a2c465e647ed7
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt;, fonctions

  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 Échange les éléments de deux vecteurs.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Le vecteur qui fournit les éléments à permuter, ou le vecteur dont les éléments doivent être échangés avec ceux du vecteur ` left`.  
  
 ` left`  
 Le vecteur dont les éléments doivent être échangés avec ceux du vecteur ` right`.  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle est un algorithme spécialisé sur la classe de conteneur vector pour exécuter la fonction membre ` left.` [vector::swap](../standard-library/vector-class.md) *( right*). Il s’agit d’instances de l’ordonnancement partiel des modèles de fonctions par le compilateur. Quand des fonctions de modèle sont surchargées de sorte que la correspondance du modèle avec l’appel de fonction n’est pas unique, le compilateur sélectionne la version la plus spécialisée de la fonction de modèle. La version générale de la fonction de modèle, **template** \< **class T**> **void swap**( **T&**, **T&**), dans la classe d’algorithme fonctionne par assignation et est une opération lente. La version spécialisée dans chaque conteneur est beaucoup plus rapide, car elle peut fonctionner avec la représentation interne de la classe de conteneur.  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise la version de modèle de `swap`, consultez l’exemple de code de la fonction membre [vector::swap](../standard-library/vector-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [\<vector>](../standard-library/vector.md)


