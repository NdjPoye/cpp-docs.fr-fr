---
title: IDBPropertiesImpl::GetProperties | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 47286d409f6bc9ffe99faffe46db58245c958f92
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
Retourne les valeurs des propriétés dans les groupes de propriétés de Source de données, sources de données et d’initialisation qui sont actuellement définies sur l’objet de source de données ou les valeurs des propriétés dans le groupe de propriétés d’initialisation qui sont actuellement définies sur le énumérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) dans les *de référence du programmeur OLE DB*.  
  
 Certains paramètres correspondent aux *de référence du programmeur OLE DB* des noms différents, qui sont décrits dans les paramètres **IDBProperties::GetProperties**:  
  
|Paramètres de modèle OLE DB|*Référence du programmeur OLE DB* paramètres|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>Notes  
 Si le fournisseur est initialisé, cette méthode retourne les valeurs des propriétés dans le **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** groupes de propriétés qui sont actuellement définies sur l’objet de source de données. Si le fournisseur n’est pas initialisé, elle retourne **DBPROPSET_DBINIT** uniquement les propriétés de groupe.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Idbpropertiesimpl, classe](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)