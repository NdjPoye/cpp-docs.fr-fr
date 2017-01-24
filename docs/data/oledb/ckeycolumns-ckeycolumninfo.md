---
title: "CKeyColumns, CKeyColumnInfo | Microsoft Docs"
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
  - "m_nColumnPropID"
  - "ORDINAL_POSITION"
  - "m_nOrdinalPosition"
  - "COLUMN_GUID"
  - "CKeyColumnInfo"
  - "CONSTRAINT_NAME"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szConstraintSchema"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "CKeyColumns"
  - "m_szTableName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "m_szConstraintName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyColumnInfo (classe de paramètre)"
  - "CKeyColumns (classe typedef)"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_nOrdinalPosition"
  - "m_szColumnName"
  - "m_szConstraintCatalog"
  - "m_szConstraintName"
  - "m_szConstraintSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "ORDINAL_POSITION"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 40525a4f-a9cf-4e9f-886d-8a6ddd18a3d6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CKeyColumns, CKeyColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe typedef **CKeyColumns** pour implémenter sa classe paramètre **CKeyColumnInfo**.  
  
## Notes  
 Voir [Classes d'ensemble de lignes d'un schéma et classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe identifie les colonnes, définies dans le catalogue, qui sont contraintes en tant que clés par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir le [Ensemble de lignes KEY\_COLUMN\_USAGE](https://msdn.microsoft.com/en-us/library/ms712990.aspx) dans *Guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Membres de données|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szConstraintCatalog|CONSTRAINT\_CATALOG|  
|m\_szConstraintSchema|CONSTRAINT\_SCHEMA|  
|m\_szConstraintName|CONSTRAINT\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_nOrdinalPosition|ORDINAL\_POSITION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)