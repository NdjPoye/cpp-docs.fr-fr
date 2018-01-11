---
title: IRowsetUpdateImpl::GetPendingRows | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
dev_langs: C++
helpviewer_keywords: GetPendingRows method
ms.assetid: 2d1ef748-da6d-4184-98dc-096427358dfd
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c8341c6013417daa8b86e484350c67be1752ba6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplgetpendingrows"></a>IRowsetUpdateImpl::GetPendingRows
Retourne une liste des lignes avec des modifications en attente.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD ( GetPendingRows )(  
   HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hReserved`  
 [in] Correspond à la `hChapter` paramètre dans [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx).  
  
 Pour les autres paramètres, consultez [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)