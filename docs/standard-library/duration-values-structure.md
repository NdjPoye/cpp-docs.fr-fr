---
title: duration_values, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs: C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0f06646975d694ab76477a64642c03c20769c54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
|[max](#max)|Static. Spécifie la limite supérieure pour une valeur de type `Rep`.|  
|[min](#min)|Static. Spécifie la limite inférieure pour une valeur de type `Rep`.|  
|[zéro](#zero)|Static. Retourne `Rep(0)`.|  
  
## <a name="requirements"></a>Configuration requise  
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

