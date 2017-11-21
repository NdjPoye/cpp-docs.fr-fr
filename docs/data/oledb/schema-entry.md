---
title: SCHEMA_ENTRY | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SCHEMA_ENTRY
dev_langs: C++
helpviewer_keywords: SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0919f2ba6474633d98c73cde758dbe6c81549f4f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Associe un GUID à une classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### <a name="parameters"></a>Paramètres  
 `guid`  
 Un GUID de lignes du schéma. Consultez [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *de référence du programmeur OLE DB* pour obtenir la liste des ensembles de lignes de schéma et les GUID.  
  
 *rowsetClass*  
 La classe qui sera créée pour représenter l’ensemble de lignes de schéma.  
  
## <a name="remarks"></a>Remarques  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) peut ensuite la carte pour obtenir la liste des GUID de requête, ou créer un ensemble de lignes si elle se voit accorder un GUID. L’ensemble de lignes de schéma `IDBSchemaRowsetImpl` crée est similaire à une norme `CRowsetImpl`-classe dérivée, mais elle doit fournir une **Execute** méthode dont la signature suivante :  
  
```  
HRESULT Execute (
    LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Cela **Execute** fonction remplit les données de l’ensemble de lignes. L’Assistant Projet ATL crée, comme décrit dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *de référence du programmeur OLE DB*, trois initiale des ensembles de lignes de schéma dans le projet pour chacun des trois schémas OLE DB obligatoires :  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **SCHÉMA DBSCHEMA_PROVIDER_TYPES**  
  
 L’Assistant ajoute également trois entrées correspondantes dans le mappage de schéma. Consultez [création d’un fournisseur OLE DB modèle](../../data/oledb/creating-an-ole-db-provider.md) pour plus d’informations sur l’utilisation de l’Assistant pour créer un fournisseur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)