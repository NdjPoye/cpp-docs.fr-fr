---
title: IRowsetImpl::SetDBStatus | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs: C++
helpviewer_keywords: SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 285f9004c9971d18646626b7410dcb52485227c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Définit le `DBSTATUS` indicateurs d’état pour le champ spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `statusFlags`  
 Le [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) indicateurs à définir pour la colonne.  
  
 `currentRow`  
 La ligne actuelle.  
  
 *columnInfo*  
 La colonne pour laquelle l’état est défini.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Le fournisseur substitue cette fonction pour fournir un traitement spécial pour **DBSTATUS_S_ISNULL** et **DBSTATUS_S_DEFAULT**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)