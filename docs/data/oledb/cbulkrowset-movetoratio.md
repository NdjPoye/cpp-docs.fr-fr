---
title: CBulkRowset::MoveToRatio | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs: C++
helpviewer_keywords: MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 98536344e3282008ace529565e6c8d805b546ef2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
Extrait les lignes à partir d’une position décimale dans l’ensemble de lignes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nNumerator`  
 [in] Le numérateur est utilisé pour déterminer la position des fractions de seconde à partir de laquelle extraire des données.  
  
 `nDenominator`  
 [in] Le dénominateur permet de déterminer la position de fractions de seconde à partir de laquelle extraire des données.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 `MoveToRatio`extrait les lignes à peu près en fonction de la formule suivante :  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Où `RowsetSize` est la taille de l’ensemble de lignes, mesurée en lignes. La précision de cette formule varie selon le fournisseur spécifique. Pour plus d’informations, consultez [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)