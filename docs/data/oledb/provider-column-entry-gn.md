---
title: PROVIDER_COLUMN_ENTRY_GN | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_GN
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_GN macro
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff73cda1e676387b4f8ca79ce1ef7cbf8fce13e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="providercolumnentrygn"></a>PROVIDER_COLUMN_ENTRY_GN
Représente une colonne spécifique pris en charge par le fournisseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### <a name="parameters"></a>Paramètres  
 *name*  
 [in] Le nom de colonne.  
  
 `ordinal`  
 [in] Le numéro de colonne. Sauf si la colonne est une colonne de signet, le numéro de colonne ne doit pas être 0.  
  
 `flags`  
 [in] Spécifie la manière dont les données sont retournées. Consultez le `dwFlags` description dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 [in] La taille de la colonne.  
  
 `dbtype`  
 [in] Indique le type de données de la valeur. Consultez le **wType** description dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *precision*  
 [in] Indique la précision à utiliser lors de l’obtention des données si *dbType* est `DBTYPE_NUMERIC` ou **DBTYPE_DECIMAL**. Consultez le **bPrecision** description dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 [in] Indique l’échelle à utiliser lors de l’obtention des données si dbType est `DBTYPE_NUMERIC` ou **DBTYPE_DECIMAL**. Consultez le **bScale** description dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Un GUID de lignes du schéma. Consultez [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *de référence du programmeur OLE DB* pour obtenir la liste des ensembles de lignes de schéma et les GUID.  
  
## <a name="remarks"></a>Notes  
 Vous permet de spécifier la taille de la colonne, type de données, précision, échelle et de lignes du schéma GUID.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)