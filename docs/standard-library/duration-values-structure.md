---
title: duration_values, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8b0c02d4edc3a460f166cb65b312ef78337d403f
ms.lasthandoff: 02/24/2017

---
# <a name="durationvalues-structure"></a>duration_values, structure
Fournit des valeurs spécifiques pour le paramètre de modèle [duration](../standard-library/duration-class.md) `Rep`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[duration_values::max](#duration_values__max_method)|Static. Spécifie la limite supérieure pour une valeur de type `Rep`.|  
|[duration_values::min](#duration_values__min_method)|Static. Spécifie la limite inférieure pour une valeur de type `Rep`.|  
|[duration_values::zero](#duration_values__zero_method)|Static. Retourne `Rep(0)`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
##  <a name="a-namedurationvaluesmaxmethoda--durationvaluesmax"></a><a name="duration_values__max_method"></a>  duration_values::max  
 Méthode statique qui retourne la limite supérieure des valeurs de type `Ref`.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `numeric_limits<Rep>::max()`.  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être supérieure à [duration_values::zero](#duration_values__zero_method).  
  
##  <a name="a-namedurationvaluesminmethoda--durationvaluesmin"></a><a name="duration_values__min_method"></a>  duration_values::min  
 Méthode statique qui retourne la limite inférieure des valeurs de type `Ref`.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `numeric_limits<Rep>::lowest()`.  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être inférieure ou égale à [duration_values::zero](#duration_values__zero_method).  
  
##  <a name="a-namedurationvalueszeromethoda--durationvalueszero"></a><a name="duration_values__zero_method"></a>  duration_values::zero  
 Retourne `Rep(0)`.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l'utilisateur, la valeur de retour doit représenter l'infini additif.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


