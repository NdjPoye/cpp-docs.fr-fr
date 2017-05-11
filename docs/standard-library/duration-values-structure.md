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
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: b170debfdb4759b41963bc0faca13b3db11ad39a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="durationvalues-structure"></a>duration_values, structure
Fournit des valeurs spécifiques pour le paramètre de modèle [duration](../standard-library/duration-class.md) `Rep`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Rep>  
struct duration_values;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>Méthodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[max](#max)|Static. Spécifie la limite supérieure pour une valeur de type `Rep`.|  
|[min](#min)|Static. Spécifie la limite inférieure pour une valeur de type `Rep`.|  
|[zéro](#zero)|Static. Retourne `Rep(0)`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<chrono >  
  
 **Espace de noms :** std::chrono  
  
##  <a name="max"></a>  duration_values::max  
 Méthode statique qui retourne la limite supérieure des valeurs de type `Ref`.  
  
```  
static constexpr Rep max();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `numeric_limits<Rep>::max()`.  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être supérieure à [duration_values::zero](#zero).  
  
##  <a name="min"></a>  duration_values::min  
 Méthode statique qui retourne la limite inférieure des valeurs de type `Ref`.  
  
```  
static constexpr Rep min();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `numeric_limits<Rep>::lowest()`.  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l’utilisateur, la valeur de retour doit être inférieure ou égale à [duration_values::zero](#zero).  
  
##  <a name="zero"></a>  duration_values::zero  
 Retourne `Rep(0)`.  
  
```  
static constexpr Rep zero();
```  
  
### <a name="remarks"></a>Notes  
 Quand `Rep` est un type défini par l'utilisateur, la valeur de retour doit représenter l'infini additif.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


