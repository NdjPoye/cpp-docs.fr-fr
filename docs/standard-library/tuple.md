---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
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
ms.openlocfilehash: 7771de57070961751e16294bc966e08843baef4c
ms.lasthandoff: 02/24/2017

---
# <a name="lttuplegt"></a>&lt;tuple&gt;
Définit un modèle `tuple` dont les instances détiennent des objets de types variables.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <tuple>  
```  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[tuple](../standard-library/tuple-class.md)|Encapsule une séquence d’éléments de longueur fixe.|  
|[tuple_element, classe](../standard-library/tuple-element-class-tuple.md)|Encapsule le type d'un élément `tuple`.|  
|[tuple_size, classe](../standard-library/tuple-size-class-tuple.md)|Encapsule le nombre d'éléments `tuple`.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator==](../standard-library/tuple-operators.md#operator_eq_eq)|Comparaison d’objets `tuple`, égal|  
|[operator!=](../standard-library/tuple-operators.md#operator_neq)|Comparaison d’objets `tuple`, non égal|  
|[operator<](../standard-library/tuple-operators.md#operator_lt_)|Comparaison d’objets `tuple`, inférieur à|  
|[operator<=](../standard-library/tuple-operators.md#operator_lt__eq)|Comparaison d’objets `tuple`, inférieur ou égal à|  
|[operator>](../standard-library/tuple-operators.md#operator_gt_)|Comparaison d’objets `tuple`, supérieur à|  
|[operator>=](../standard-library/tuple-operators.md#operator_gt__eq)|Comparaison d’objets `tuple`, supérieur ou égal à|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get_function)|Obtient un élément auprès d'un objet `tuple`.|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple_function)|Crée un `tuple` à partir des valeurs de l’élément.|  
|[tie](../standard-library/tuple-functions.md#tie_function)|Crée un `tuple` à partir des références d’élément.|  
  
## <a name="see-also"></a>Voir aussi  
 [\<array>](../standard-library/array.md)


