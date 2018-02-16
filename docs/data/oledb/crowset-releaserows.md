---
title: CRowset::ReleaseRows | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ReleaseRows
- CRowset::ReleaseRows
- ATL::CRowset<TAccessor>::ReleaseRows
- CRowset<TAccessor>.ReleaseRows
- CRowset.ReleaseRows
- ATL.CRowset.ReleaseRows
- ATL.CRowset<TAccessor>.ReleaseRows
- CRowset<TAccessor>::ReleaseRows
- ATL::CRowset::ReleaseRows
dev_langs:
- C++
helpviewer_keywords:
- ReleaseRows method
ms.assetid: fa7254f5-566f-4754-bdf7-d0874256926f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c05d01de41e3d39e427a8eb24c47a456cc6955c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetreleaserows"></a>CRowset::ReleaseRows
Appels [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) pour libérer le handle de ligne actuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ReleaseRows() throw();  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)