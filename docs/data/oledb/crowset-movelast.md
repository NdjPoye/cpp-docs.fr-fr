---
title: CRowset::MoveLast | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset<TAccessor>::MoveLast
- CRowset<TAccessor>::MoveLast
- ATL.CRowset.MoveLast
- ATL::CRowset::MoveLast
- CRowset<TAccessor>.MoveLast
- MoveLast
- CRowset::MoveLast
- ATL.CRowset<TAccessor>.MoveLast
- CRowset.MoveLast
dev_langs: C++
helpviewer_keywords: MoveLast method
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d57885232fb10f302aeb36c6c074e7a88f0fb67b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovelast"></a>CRowset::MoveLast
Déplace le curseur vers la dernière ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Appels [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) pour redéfinir l’emplacement d’extraction suivant à la dernière position et récupère la dernière ligne.  
  
 Cette méthode requiert que vous définissez **DBPROP_CANSCROLLBACKWARDS** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes. (Pour de meilleures performances, vous pouvez également définir **DBPROP_QUICKRESTART** à `VARIANT_TRUE`.)  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)