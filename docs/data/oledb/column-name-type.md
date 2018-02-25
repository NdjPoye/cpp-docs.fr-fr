---
title: COLUMN_NAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLUMN_NAME_TYPE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_TYPE macro
ms.assetid: 815ace8f-8ec3-4ad7-a7a0-37fa8e4bc68c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6294efd7a1b78a53673d5df7d9a051e852604edf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="columnnametype"></a>COLUMN_NAME_TYPE
Représente une liaison sur l’ensemble de lignes à la colonne dans l’ensemble de lignes. Semblable à [COLUMN_NAME](../../data/oledb/column-name.md), sauf que cette macro prend également le type de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
COLUMN_NAME_TYPE(pszName, wType, data)  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszName`  
 [in] Pointeur vers le nom de colonne. Le nom doit être une chaîne Unicode. Vous pouvez le faire en plaçant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 `wType`  
 [in] Le type de données.  
  
 `data`  
 [in] Le membre de données correspondant dans l’enregistrement utilisateur.  
  
## <a name="remarks"></a>Notes  
 Consultez [COLUMN_NAME](../../data/oledb/column-name.md) pour plus d’informations sur la **COLUMN_NAME_\***  macros sont utilisées.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)