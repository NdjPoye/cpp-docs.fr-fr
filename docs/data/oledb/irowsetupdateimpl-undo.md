---
title: IRowsetUpdateImpl::Undo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
dev_langs: C++
helpviewer_keywords: Undo method
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 329a6141ca01678c341ef3890fb0e563a7299915
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplundo"></a>IRowsetUpdateImpl::Undo
Annule toutes les modifications à la ligne depuis la dernière extraction ou de la mise à jour.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD ( Undo )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hReserved`  
 [in] Correspond à la `hChapter` paramètre dans [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 [out] Correspond à la `pcRows` paramètre dans [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 [in] Correspond à la *prgRows* paramètre dans [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx).  
  
 Pour les autres paramètres, consultez [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)