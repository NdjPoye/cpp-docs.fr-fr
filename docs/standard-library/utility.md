---
title: '&lt;utility&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <utility>
- utility/std::<utility>
- std.<utility>
- std::<utility>
dev_langs:
- C++
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 67792e92a4a8336c025249a5d1322d00360a62c5
ms.lasthandoff: 02/24/2017

---
# <a name="ltutilitygt"></a>&lt;utility&gt;
Définit des types, des fonctions et des opérateurs de la bibliothèque standard C++ qui aident à construire et à gérer des paires d’objets qui sont utiles quand deux objets doivent être traités comme s’ils n’en étaient qu’un seul.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <utility>  
  
```  
  
## <a name="remarks"></a>Notes  
 Les paires sont largement utilisées dans la bibliothèque standard C++. Elles sont nécessaires comme arguments et valeurs de retour pour diverses fonctions et comme types d’éléments pour des conteneurs tels que la [classe map](../standard-library/map-class.md) et la [classe multimap](../standard-library/multimap-class.md). L’en-tête \<utility> est inclus automatiquement par \<map> pour aider à gérer leurs éléments de type paire clé/valeur.  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Classe qui encapsule le type d'un élément `pair`.|  
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Classe qui encapsule le nombre d'éléments `pair`.|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[forward](../standard-library/utility-functions.md#forward)|Empêche que le type de référence (`lvalue` ou `rvalue`) de l'argument ne soit masqué par le transfert parfait.|  
|[get](../standard-library/utility-functions.md#get)|Fonction qui obtient un élément d'un objet `pair`.|  
|[make_pair](../standard-library/utility-functions.md#make_pair)|Fonction d'assistance de modèle qui sert à construire des objets de type `pair`, où les types de composants sont basés sur les types de données passés comme paramètres.|  
|[move](../standard-library/utility-functions.md#move)|Retourne l'argument passé comme référence `rvalue`.|  
|[swap](../standard-library/utility-functions.md#swap)|Échange les éléments de deux objets `pair`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator!=](../standard-library/utility-operators.md#operator_neq)|Teste si l'objet pair situé à gauche de l'opérateur n'est pas égal à l'objet pair situé à droite.|  
|[operator==](../standard-library/utility-operators.md#operator_eq_eq)|Teste si l'objet pair situé à gauche de l'opérateur est égal à l'objet pair situé à droite.|  
|[operator<](../standard-library/utility-operators.md#operator_lt_)|Teste si l'objet pair situé à gauche de l'opérateur est inférieur à l'objet pair situé à droite.|  
|[operator\<=](../standard-library/utility-operators.md#operator_lt__eq)|Teste si l'objet pair situé à gauche de l'opérateur est inférieur ou égal à l'objet pair situé à droite.|  
|[operator>](../standard-library/utility-operators.md#operator_gt_)|Teste si l'objet pair situé à gauche de l'opérateur est supérieur à l'objet pair situé à droite.|  
|[operator>=](../standard-library/utility-operators.md#operator_gt__eq)|Teste si l'objet pair situé à gauche de l'opérateur est supérieur ou égal à l'objet pair situé à droite.|  
  
### <a name="structs"></a>Structures  
  
|||  
|-|-|  
|[identity](../standard-library/identity-structure.md)||  
|[pair](../standard-library/pair-structure.md)|Struct qui permet de traiter deux objets comme s'il s'agissait d'un objet unique.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




