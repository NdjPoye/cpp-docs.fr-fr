---
title: "CConstraintColumnUsage, CConstraintColumnUsageInfo | Microsoft Docs"
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
  - "m_szConstraintCatalog"
  - "CConstraintColumnUsage"
  - "m_nColumnPropID"
  - "COLUMN_GUID"
  - "CONSTRAINT_NAME"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szConstraintSchema"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "CONSTRAINT_COLUMN_USAGE"
  - "m_szTableName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "CConstraintColumnUsageInfo"
  - "m_szConstraintName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConstraintColumnUsage (classe typedef)"
  - "CConstraintColumnUsageInfo (classe de paramètre)"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_COLUMN_USAGE"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szColumnName"
  - "m_szConstraintCatalog"
  - "m_szConstraintName"
  - "m_szConstraintSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 7d4d94e8-2025-4fcc-a176-c9b231eca77b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CConstraintColumnUsage, CConstraintColumnUsageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CConstraintColumnUsage** de typedef pour implémenter la classe de paramètre **CConstraintColumnUsageInfo**.  
  
## Notes  
 Voir [Classes d'ensemble de lignes d'un schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe identifie les colonnes utilisées par les contraintes référentielles, les contraintes uniques, les contraintes de validation et les assertions, définies dans le catalogue et détenues par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Consultez [Ensemble de lignes CONSTRAINT\_USAGE\_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms724522.aspx) dans le *guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Membres de données|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_szConstraintCatalog|CONSTRAINT\_CATALOG|  
|m\_szConstraintSchema|CONSTRAINT\_SCHEMA|  
|m\_szConstraintName|CONSTRAINT\_NAME|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)