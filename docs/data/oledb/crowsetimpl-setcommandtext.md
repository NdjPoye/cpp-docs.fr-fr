---
title: CRowsetImpl::SetCommandText | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e345799f74d4c32ffae88baebb69ed828266dcfc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
Valide et stocke le **DBID**s dans les deux chaînes ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pTableID`  
 [in] Un pointeur vers le **DBID** représentant l’ID de table.  
  
 `pIndexID`  
 [in] Un pointeur vers le **DBID** représentant l’ID d’index.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Le **SetCommentText** méthode est appelée par `CreateRowset`, statique transformer en modèle de méthode de `IOpenRowsetImpl`.  
  
 Cette méthode délègue son travail en appelant [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) et [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) via un pointeur converti en supertype.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)