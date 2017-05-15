---
title: '&lt;map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<map>
- std.<map>
- <map>
dev_langs:
- C++
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: c9a97acb8bf6154bfba764049f1082fc0cca8055
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltmapgt"></a>&lt;map&gt;
Définit les classes de modèle de conteneur map et multimap et leurs modèles de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <map>  
  
```  
  
## <a name="members"></a>Membres  
  
### <a name="operators"></a>Opérateurs  
  
|Version map|Version multimap|Description|  
|-----------------|----------------------|-----------------|  
|[operator!= (map)](../standard-library/map-operators.md#op_neq)|[operator!= (multimap)](../standard-library/map-operators.md#op_neq)|Teste si l'objet map ou multimap situé à gauche de l'opérateur n'est pas égal à l'objet map ou multimap situé à droite.|  
|[operator< (map)](../standard-library/map-operators.md#op_eq_eq)|[operator< (multimap)](../standard-library/map-operators.md#op_eq_eq)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est inférieur à l'objet map ou multimap situé à droite.|  
|[operator<= (map)](../standard-library/map-operators.md#op_lt)|[operator\<= (multimap)](../standard-library/map-operators.md#op_lt)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est inférieur ou égal à l'objet map ou multimap situé à droite.|  
|[operator== (map)](../standard-library/map-operators.md#op_eq_eq)|[operator== (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est égal à l'objet map ou multimap situé à droite.|  
|[operator> (map)](../standard-library/map-operators.md#op_gt)|[operator> (multimap)](../standard-library/map-operators.md#op_gt_multimap)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est supérieur à l'objet map ou multimap situé à droite.|  
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[operator>= (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est supérieur ou égal à l'objet map ou multimap situé à droite.|  
  
### <a name="specialized-template-functions"></a>Fonctions avec modèle spécialisé  
  
|Version map|Version multimap|Description|  
|-----------------|----------------------|-----------------|  
|[swap (map)](../standard-library/map-functions.md#swap)|[swap (multimap)](../standard-library/map-functions.md#swap_multimap)|Échange les éléments de deux classes map ou multimap.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[value_compare, classe](../standard-library/value-compare-class-map.md)|Fournit un objet de fonction qui peut comparer les éléments d'un map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le map.|  
|[map, classe](../standard-library/map-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle chacun des éléments a une clé unique avec laquelle les données sont automatiquement triées.|  
|[multimap, classe](../standard-library/multimap-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle chacun des éléments a une clé avec laquelle les données sont automatiquement triées et les clés ne doivent pas obligatoirement avoir des valeurs uniques.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)




