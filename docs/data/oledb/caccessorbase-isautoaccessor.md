---
title: CAccessorBase::IsAutoAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs:
- C++
helpviewer_keywords:
- IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 304727142b6a3afb293b33c01746743118fa3a64
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
Retourne la valeur true si les données sont récupérées automatiquement pour l’accesseur pendant une opération de déplacement.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
      bool IsAutoAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nAccessor`  
 [in] Le nombre de décalage de zéro pour l’accesseur.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne **true** si l’accesseur est un auto-accesseur. Sinon, elle retourne **False**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CAccessorBase, classe](../../data/oledb/caccessorbase-class.md)