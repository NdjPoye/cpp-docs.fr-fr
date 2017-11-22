---
title: atomic_flag, structure | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 94ab743545518fdaa9baa7817b4865673e2d8e56
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="atomicflag-structure"></a>atomic_flag, structure
Décrit un objet qui définit et efface atomiquement un indicateur `bool`. Les opérations sur les indicateurs atomiques sont toujours sans verrou.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct atomic_flag;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[clear](#clear)|Définit l’indicateur stocké avec la valeur `false`.|  
|[test_and_set](#test_and_set)|Définit l’indicateur stockée avec la valeur `true` et retourne la valeur initiale de l’indicateur.|  
  
## <a name="remarks"></a>Notes  
 Les objets `atomic_flag` peuvent être passés aux fonctions non-membres [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) et [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit). Ils peuvent être initialisés à l’aide de la valeur `ATOMIC_FLAG_INIT`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<atomique >  
  
 **Espace de noms :** std  
  
##  <a name="clear"></a>atomic_flag::Clear
 Définit l’indicateur `bool` stocké dans `*this` avec la valeur `false`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées.  
  
```
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="test_and_set"></a>atomic_flag::test_and_set
 Définit l’indicateur `bool` stocké dans `*this` avec la valeur `true`, en respectant les contraintes [memory_order](../standard-library/atomic-enums.md#memory_order_enum) spécifiées.  
  
```
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Order`  
 Une énumération [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur initiale de l’indicateur est stockée dans `*this`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<atomic>](../standard-library/atomic.md)



