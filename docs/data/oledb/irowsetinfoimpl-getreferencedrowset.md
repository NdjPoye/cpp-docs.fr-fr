---
title: IRowsetInfoImpl::GetReferencedRowset | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
dev_langs: C++
helpviewer_keywords: GetReferencedRowset method
ms.assetid: 94d2155c-9da0-4c19-a37c-bc35716359fd
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 24ab901af1d663434a20e4cf70301ea965ca237d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetinfoimplgetreferencedrowset"></a>IRowsetInfoImpl::GetReferencedRowset
Retourne un pointeur d’interface à l’ensemble de lignes auquel s’applique un signet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD ( GetReferencedRowset )(  
   DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/en-us/library/ms721145.aspx) dans les *de référence du programmeur OLE DB*. Le *iOrdinal* le paramètre doit être une colonne de signet.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Irowsetinfoimpl, classe](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)