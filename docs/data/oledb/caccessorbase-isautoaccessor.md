---
title: CAccessorBase::IsAutoAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
dev_langs: C++
helpviewer_keywords: IsAutoAccessor method
ms.assetid: c330da15-2947-4050-ad00-8f776adc58fb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 677eb2d2ca8d719598090e1753275e2429706b83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbaseisautoaccessor"></a>CAccessorBase::IsAutoAccessor
Retourne la valeur true si les données sont récupérées automatiquement pour l’accesseur pendant une opération de déplacement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool IsAutoAccessor(  
   ULONG nAccessor   
) const;  
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