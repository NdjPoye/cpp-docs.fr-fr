---
title: IRowsetImpl::RefRows | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
dev_langs: C++
helpviewer_keywords: RefRows method
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c1e39eb09ebfd3d93dd8302591db3406a8154449
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplrefrows"></a>IRowsetImpl::RefRows
Appelé par [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) et [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) à incrémenter ou libérer un décompte de références à un handle de ligne existant.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT RefRows(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)   
 [CSimpleRow, classe](../../data/oledb/csimplerow-class.md)