---
title: IRowsetLocateImpl::Compare | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9eaa0aaecd1ff30e51416aaaccebcc8fe6746222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
Compare deux signets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="remarks"></a>Notes  
 Une des signets peuvent être une norme définie par OLE DB [signet standard](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST**, **DBBMK_LAST**, ou **DBBMK_INVALID**). La valeur retournée dans `pComparison` indique la relation entre les deux signets :  
  
-   **DBCOMPARE_LT** (`cbBookmark1` avant `cbBookmark2`.)  
  
-   **DBCOMPARE_EQ** (`cbBookmark1` est égal à `cbBookmark2`.)  
  
-   **DBCOMPARE_GT** (`cbBookmark1` après `cbBookmark2`.)  
  
-   **DBCOMPARE_NE** (les signets sont égaux, ni classés.)  
  
-   **DBCOMPARE_NOTCOMPARABLE** (les signets ne peuvent pas être comparées).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [IRowsetLocateImpl, classe](../../data/oledb/irowsetlocateimpl-class.md)