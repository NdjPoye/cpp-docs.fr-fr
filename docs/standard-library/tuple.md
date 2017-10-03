---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b84a2094205e3db7935d5768a3f86ba765487685
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

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
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Comparaison d’objets `tuple`, égal|  
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Comparaison d’objets `tuple`, non égal|  
|[operator<](../standard-library/tuple-operators.md#op_lt)|Comparaison d’objets `tuple`, inférieur à|  
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Comparaison d’objets `tuple`, inférieur ou égal à|  
|[operator>](../standard-library/tuple-operators.md#op_gt)|Comparaison d’objets `tuple`, supérieur à|  
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Comparaison d’objets `tuple`, supérieur ou égal à|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[get](../standard-library/tuple-functions.md#get)|Obtient un élément auprès d'un objet `tuple`.|  
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Crée un `tuple` à partir des valeurs de l’élément.|  
|[tie](../standard-library/tuple-functions.md#tie)|Crée un `tuple` à partir des références d’élément.|  
  
## <a name="see-also"></a>Voir aussi  
 [\<array>](../standard-library/array.md)


