---
title: IRowsetImpl::RestartPosition | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs: C++
helpviewer_keywords: RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8ed3217a635f8a0b9af5e2c94fff325e07bff61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Repositionne la prochaine position d’extraction à sa position initiale ; Autrement dit, sa position lors de l’ensemble de lignes est initialement créé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Notes  
 La position de l’ensemble de lignes n’est pas définie tant que **GetNextRow** est appelée. Vous pouvez déplacer vers l’arrière dans un rowet en appelant `RestartPosition` , puis l’extraction ou le défilement vers l’arrière.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)