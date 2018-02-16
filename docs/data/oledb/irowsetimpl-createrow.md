---
title: IRowsetImpl::CreateRow | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4403388146b79eec4435374793b2517dd46ff188
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Une méthode d’assistance appelée par [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) pour allouer une nouvelle **HROW**.  
  
## <a name="syntax"></a>Syntaxe  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
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