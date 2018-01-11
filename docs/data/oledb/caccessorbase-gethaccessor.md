---
title: CAccessorBase::GetHAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
dev_langs: C++
helpviewer_keywords: GetHAccessor method
ms.assetid: 1bb98762-0752-4aae-a0b6-ba96bec03621
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 15b598480c229c7564f0a0f9917716247c5f7dea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbasegethaccessor"></a>CAccessorBase::GetHAccessor
Récupère le handle d’accesseur d’un accesseur spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HACCESSOR GetHAccessor(  
   ULONG nAccessor   
) const;  
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