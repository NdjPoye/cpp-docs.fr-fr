---
title: "CColumnPrivileges, CColumnPrivilegeInfo | Microsoft Docs"
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
  - "CColumnPrivileges"
  - "m_bIsGrantable"
  - "m_nColumnPropID"
  - "m_szPrivilegeType"
  - "COLUMN_GUID"
  - "IS_GRANTABLE"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szGrantor"
  - "GRANTOR"
  - "GRANTEE"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "COLUMN_PRIVILEGES"
  - "m_szTableName"
  - "CColumnPrivilegeInfo"
  - "m_szGrantee"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnPrivilegeInfo (classe de paramètre)"
  - "CColumnPrivileges (classe typedef)"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PRIVILEGES"
  - "COLUMN_PROPID"
  - "GRANTEE"
  - "GRANTOR"
  - "IS_GRANTABLE"
  - "m_bIsGrantable"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_szColumnName"
  - "m_szGrantee"
  - "m_szGrantor"
  - "m_szPrivilegeType"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 245df365-421f-43c6-9fcd-fb2197c871c6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CColumnPrivileges, CColumnPrivilegeInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CColumnPrivileges** to implement its parameter class **CColumnPrivilegeInfo**.  
  
## Notes  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the privileges on columns of tables, defined in the catalog, that are available to or granted by a given user.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [COLUMN\_PRIVILEGES Rowset](https://msdn.microsoft.com/en-us/library/ms715800.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szGrantor|GRANTOR|  
|m\_szGrantee|GRANTEE|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_szPrivilegeType|PRIVILEGE\_TYPE|  
|m\_bIsGrantable|IS\_GRANTABLE|  
  
## Conditions requises  
 **Header:** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)