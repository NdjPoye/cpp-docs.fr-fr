---
title: CAccessorBase::GetHAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs:
- C++
helpviewer_keywords:
- GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 27bdf0058c2152f8797be54b28eeee7ac3e21135
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Récupère le handle d’accesseur d’un accesseur spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
      HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nAccessor`  
 [in] Le nombre de décalage de zéro pour l’accesseur.  
  
## <a name="return-value"></a>Valeur de retour  
 Le handle d’accesseur.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CAccessorBase, classe](../../data/oledb/caccessorbase-class.md)