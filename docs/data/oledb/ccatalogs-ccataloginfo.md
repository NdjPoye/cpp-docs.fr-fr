---
title: "CCatalogs, CCatalogInfo | Microsoft Docs"
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
  - "CCatalogs"
  - "m_szName"
  - "CCatalogInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCatalogInfo (classe de paramètre)"
  - "CCatalogs (classe typedef)"
  - "DESCRIPTION (classe) (données membres)"
  - "m_szDescription"
  - "m_szName"
ms.assetid: 8362cbbd-2f00-4272-8518-fc235c4de193
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCatalogs, CCatalogInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CCatalogs** to implement its parameter class **CCatalogInfo**.  
  
## Notes  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the physical attributes associated with catalogs accessible from the DBMS.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [CATALOGS Rowset](https://msdn.microsoft.com/en-us/library/ms721241.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szName|CATALOG\_NAME|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **Header:** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)