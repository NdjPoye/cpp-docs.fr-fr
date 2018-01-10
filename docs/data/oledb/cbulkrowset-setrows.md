---
title: CBulkRowset::SetRows | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs: C++
helpviewer_keywords: SetRows method
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87fdb1f634c39062252c2593ae0a5b92d6265660
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetsetrows"></a>CBulkRowset::SetRows
Définit le nombre de descripteurs de lignes récupérées par chaque appel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void SetRows(  
   DBROWCOUNT nRows   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nRows`  
 [in] La nouvelle taille de l’ensemble de lignes (nombre de lignes).  
  
## <a name="remarks"></a>Notes  
 Si vous appelez cette fonction, il doit être avant l’ouverture de l’ensemble de lignes.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)