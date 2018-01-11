---
title: CViewColumnUsage, CViewColumnInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szTableSchema
- m_szCatalog
- m_nColumnPropID
- COLUMN_GUID
- m_szColumnName
- m_szTableCatalog
- CViewColumnInfo
- m_szSchema
- CViewColumnUsage
- COLUMN_PROPID
- m_guidColumn
- m_szTableName
- m_szName
dev_langs: C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szSchema
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- m_nColumnPropID
- CViewColumnInfo parameter class
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szName
- m_szTableCatalog
- CViewColumnUsage typedef class
- m_szTableName
- COLUMN_GUID
- m_guidColumn
ms.assetid: 4af14d6b-b224-4d72-b035-9d3aaacde32f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 74f2e2a76934f30c5b65a83c6570d14ccebd1fc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cviewcolumnusage-cviewcolumninfo"></a>CViewColumnUsage, CViewColumnInfo
Appelez la classe typedef **CViewColumnUsage** pour implémenter sa classe de paramètre **CViewColumnInfo**.  
  
## <a name="remarks"></a>Notes  
 Consultez [Classes de jeu de lignes de schéma et Classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d’informations sur l’utilisation de classes typedef.  
  
 Cette classe identifie les colonnes sur laquelle afficher les tables définies dans le catalogue et détenues par un utilisateur donné, sont dépendantes.  
  
 Le tableau suivant répertorie les membres de données de la classe et les colonnes correspondantes de OLE DB. Consultez [ensemble de lignes VIEW_COLUMN_USAGE](https://msdn.microsoft.com/en-us/library/ms714896.aspx) dans les *de référence du programmeur OLE DB* pour plus d’informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes de OLE DB|  
|------------------|--------------------|  
|m_szCatalog|VIEW_CATALOG|  
|m_szSchema|VIEW_SCHEMA|  
|m_szName|VIEW_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbsch.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)