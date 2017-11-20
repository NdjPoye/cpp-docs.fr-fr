---
title: BLOB_ENTRY_STATUS | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_STATUS
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_STATUS macro
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0cc0805147908703b880cb826b0363acecfa4902
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrystatus"></a>BLOB_ENTRY_STATUS
Utilisé avec `BEGIN_COLUMN_MAP` ou `BEGIN_ACCESSOR_MAP` pour lier un objet binaire volumineux ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Semblable à [BLOB_ENTRY](../../data/oledb/blob-entry.md), sauf que cette macro obtient également l’état de la colonne BLOB.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BLOB_ENTRY_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
status  
 )  
  
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
  
 *status*  
 [out] L’état du champ BLOB.  
  
## <a name="example"></a>Exemple  
 Consultez [comment récupérer un objet BLOB ?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)