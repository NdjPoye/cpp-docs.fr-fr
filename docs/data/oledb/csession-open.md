---
title: CSession::Open | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7ab796d19c45959aac608de5097e9112bd8543e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="csessionopen"></a>CSession::Open
Ouvre une nouvelle session de l’objet de source de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ds`  
 [in] La source de données pour lequel la session doit être ouvert.  
  
 *pPropSet*  
 [in] Un pointeur vers un tableau de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) les structures contenant des propriétés et valeurs à définir. Consultez [jeux de propriétés et des groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans les *de référence du programmeur OLE DB* dans le Kit de développement logiciel Windows.  
  
 `ulPropSets`  
 [in] Le nombre de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures passées dans le *pPropSet* argument.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Vous devez ouvrir l’objet de source de données à l’aide [CDataSource::Open](../../data/oledb/cdatasource-open.md) avant leur transmission à `CSession::Open`.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CSession, classe](../../data/oledb/csession-class.md)