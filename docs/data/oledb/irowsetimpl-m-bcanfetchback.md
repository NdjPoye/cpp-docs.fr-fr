---
title: IRowsetImpl::m_bCanFetchBack | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
dev_langs: C++
helpviewer_keywords: m_bCanFetchBack
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7ba8cacdb172158f2afdb5574dd58e2db7e922bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbcanfetchback"></a>IRowsetImpl::m_bCanFetchBack
Indique si un fournisseur prend en charge l’extraction vers l’arrière.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## <a name="remarks"></a>Notes  
 Lié à la **DBPROP_CANFETCHBACKWARDS** propriété dans le **DBPROPSET_ROWSET** groupe. Le fournisseur doit prendre en charge **DBPROP_CANFETCHBACKWARDS** pour **m_bCanFetchBackwards** avoir la valeur true.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)