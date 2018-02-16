---
title: BLOB_ENTRY_LENGTH_STATUS | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BLOB_ENTRY_LENGTH_STATUS
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY_LENGTH_STATUS macro
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3170371682471204fd3c59997d630642bf3cd6b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="blobentrylengthstatus"></a>BLOB_ENTRY_LENGTH_STATUS
Utilisé avec `BEGIN_COLUMN_MAP` et `END_COLUMN_MAP` pour lier un objet binaire volumineux ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Semblable à [BLOB_ENTRY](../../data/oledb/blob-entry.md), sauf que cette macro obtient également la longueur et l’état de la colonne BLOB.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
BLOB_ENTRY_LENGTH_STATUS(  
    nOrdinal,  
    IID,  
    flags,  
    data,
    length,
    status )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nOrdinal`  
 [in] Le numéro de colonne.  
  
 *IID*  
 [in] Interface, GUID, tels que **IDD_ISequentialStream**, utilisée pour récupérer l’objet BLOB.  
  
 `flags`  
 [in] Indicateurs de mode de stockage tel que défini par le modèle de stockage structuré OLE (par exemple, **STGM_READ**).  
  
 `data`  
 [in] Le membre de données correspondant dans l’enregistrement utilisateur.  
  
 *length*  
 [out] Longueur (réelle), en octets, de la colonne BLOB.  
  
 *status*  
 [out] L’état de la colonne de données BLOB.  
  
## <a name="example"></a>Exemple  
 Consultez [comment récupérer un objet BLOB ?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)