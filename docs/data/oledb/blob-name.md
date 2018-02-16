---
title: BLOB_NAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BLOB_NAME
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME macro
ms.assetid: 757acd0d-946d-447d-937e-94ecd700ba38
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 488c2f9cc2570ea5b512d0cf245902793d408dc5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="blobname"></a>BLOB_NAME
Utilisé avec `BEGIN_COLUMN_MAP` et `END_COLUMN_MAP` pour lier un objet binaire volumineux ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Semblable à [BLOB_ENTRY](../../data/oledb/blob-entry.md), sauf que cette macro prend un nom de colonne au lieu d’un numéro de colonne.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
BLOB_NAME(pszName, IID, flags, data )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pszName`  
 [in] Pointeur vers le nom de colonne. Le nom doit être une chaîne Unicode. Vous pouvez le faire en plaçant un « L » devant le nom, par exemple : `L"MyColumn"`.  
  
 *IID*  
 [in] Interface, GUID, tels que **IDD_ISequentialStream**, utilisée pour récupérer l’objet BLOB.  
  
 `flags`  
 [in] Indicateurs de mode de stockage tel que défini par le modèle de stockage structuré OLE (par exemple, **STGM_READ**).  
  
 `data`  
 [in] Le membre de données correspondant dans l’enregistrement utilisateur.  
  
## <a name="example"></a>Exemple  
 Consultez [comment récupérer un objet BLOB ?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)