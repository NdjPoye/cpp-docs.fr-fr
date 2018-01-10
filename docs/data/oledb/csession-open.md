---
title: CSession::Open | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3aa0f6b694bc594ec00511ce39b7887bf26ecae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csessionopen"></a>CSession::Open
Ouvre une nouvelle session de l’objet de source de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
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