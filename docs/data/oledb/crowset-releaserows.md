---
title: CRowset::ReleaseRows | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: ReleaseRows method
ms.assetid: fa7254f5-566f-4754-bdf7-d0874256926f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 779cab8b916db45d3eafc53564ad40c5036544a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetreleaserows"></a>CRowset::ReleaseRows
Appels [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) pour libérer le handle de ligne actuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
HRESULT ReleaseRows( ) throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)