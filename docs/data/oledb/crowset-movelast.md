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
ms.openlocfilehash: 8a84fd6027ef147bbbe52e8ffee5d3c7b21efd38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetmovelast"></a>CRowset::MoveLast
Déplace le curseur vers la dernière ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Remarques  
 Appels [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) pour redéfinir l’emplacement d’extraction suivant à la dernière position et récupère la dernière ligne.  
  
 Cette méthode requiert que vous définissez **DBPROP_CANSCROLLBACKWARDS** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes. (Pour de meilleures performances, vous pouvez également définir **DBPROP_QUICKRESTART** à `VARIANT_TRUE`.)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)