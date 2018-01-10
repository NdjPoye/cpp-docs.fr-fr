---
title: IRowsetImpl::CreateRow | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs: C++
helpviewer_keywords: CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f90a5de73b5eea37eea192a4886fe29d1d8b435b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Une méthode d’assistance appelée par [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) pour allouer une nouvelle **HROW**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *lRowsOffset*  
 Position du curseur de la ligne en cours de création.  
  
 *cRowsObtained*  
 Une référence est passée à l’utilisateur indiquant le nombre de lignes créées.  
  
 *rgRows*  
 Un tableau de **HROW**s retourné à l’appelant avec les poignées de ligne nouvellement créée.  
  
## <a name="remarks"></a>Notes  
 Si la ligne existe, cette méthode appelle [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) et le retourne. Dans le cas contraire, il alloue une nouvelle instance de la variable de modèle RowClass et ajoute à [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)