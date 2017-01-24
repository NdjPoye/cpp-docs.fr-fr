---
title: "CViewColumnUsage, CViewColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szTableSchema"
  - "m_szCatalog"
  - "m_nColumnPropID"
  - "COLUMN_GUID"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "CViewColumnInfo"
  - "m_szSchema"
  - "CViewColumnUsage"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "m_szTableName"
  - "m_szName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CViewColumnInfo (classe de paramètre)"
  - "CViewColumnUsage (classe typedef)"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szCatalog"
  - "m_szColumnName"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 4af14d6b-b224-4d72-b035-9d3aaacde32f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CViewColumnUsage, CViewColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CViewColumnUsage** de typedef pour implémenter sa classe de paramètre **CViewColumnInfo**.  
  
## Notes  
 Consultez [Classes d'ensemble de lignes d'un schéma et classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe identifie les colonnes dont dépendent les tables affichées, définies dans le catalogue et détenues par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir [Ensemble de lignes VIEW\_COLUMN\_USAGE](https://msdn.microsoft.com/en-us/library/ms714896.aspx) dans *Guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalog|VIEW\_CATALOG|  
|m\_szSchema|VIEW\_SCHEMA|  
|m\_szName|VIEW\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)