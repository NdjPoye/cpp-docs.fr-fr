---
title: CDBPropIDSet::CDBPropIDSet | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
dev_langs: C++
helpviewer_keywords: CDBPropIDSet class, constructor
ms.assetid: e68cc20e-fce2-4cc1-9e9d-05c542334cc8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e3967acbc41098df0278c56a71d2b077c322b9af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropidsetcdbpropidset"></a>CDBPropIDSet::CDBPropIDSet
Constructeur. Initialise le **rgProperties**, **cProperties**et (facultativement) **guidPropertySet** champs de la [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) structure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      CDBPropIDSet(  
   const GUID& guid   
);  
CDBPropIDSet(   
   const CDBPropIDSet& propidset    
);  
CDBPropIDSet( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `guid`  
 [in] Un GUID utilisé pour initialiser le **guidPropertySet** champ.  
  
 *propidset*  
 [in] Un autre `CDBPropIDSet` objet pour la construction de copie.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDBPropIDSet (classe)](../../data/oledb/cdbpropidset-class.md)   
 [CDBPropIDSet::SetGUID](../../data/oledb/cdbpropidset-setguid.md)