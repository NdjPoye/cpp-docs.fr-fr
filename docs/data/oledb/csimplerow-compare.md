---
title: CSimpleRow::Compare | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87ee21022aa379820ced0463892be12ee0676d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Compare deux lignes pour voir s’ils font référence à la même instance de ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRow`  
 Un pointeur vers un `CSimpleRow` objet.  
  
## <a name="return-value"></a>Valeur de retour  
 Un `HRESULT` valeur généralement `S_OK`, indiquant les deux lignes sont la même instance de ligne, ou **S_FALSE**, indiquant les deux lignes sont différentes. Consultez [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) dans les *de référence du programmeur OLE DB* pour d’autres valeurs de retournés possibles.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CSimpleRow (classe)](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)