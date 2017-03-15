---
title: "CTables, CTableInfo | Microsoft Docs"
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
  - "m_szCatalog"
  - "TABLE_SCHEMA"
  - "CTables"
  - "TABLE_NAME"
  - "TABLE_CATALOG"
  - "CTableInfo"
  - "m_guidTable"
  - "m_szType"
  - "m_szSchema"
  - "m_szName"
  - "TABLE_GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTableInfo (classe de paramètre)"
  - "CTables (classe typedef)"
  - "DESCRIPTION (classe) (données membres)"
  - "m_guidTable"
  - "m_szCatalog"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
  - "m_szType"
  - "TABLE_CATALOG"
  - "TABLE_GUID"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 57670f1b-ba99-43b0-b406-4c75b44f14f6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTables, CTableInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CTables** de typedef pour implémenter la classe **CTableInfo**de paramètre.  
  
## Notes  
 Consultez [Classes d'ensemble de lignes d'un schéma et classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe identifie les privilèges des tables, définis dans le catalogue, qui sont disponibles ou accordés par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Consultez [TABLES Rowset](https://msdn.microsoft.com/en-us/library/ms716980.aspx) dans le *OLE DB Programmer's Reference* pour plus d'informations sur les schémas et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalog|TABLE\_CATALOG|  
|m\_szSchema|TABLE\_SCHEMA|  
|m\_szName|TABLE\_NAME|  
|m\_szType|TABLE\_TYPE|  
|m\_guidTable|TABLE\_GUID|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)