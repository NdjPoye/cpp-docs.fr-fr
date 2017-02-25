---
title: "Macros pour les mod&#232;les du fournisseur OLE&#160;DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros, Modèles du fournisseur OLE DB"
  - "modèles du fournisseur OLE DB (macros)"
  - "modèles du fournisseur OLE DB, macros"
  - "macros des modèles du fournisseur (OLE DB)"
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Macros pour les mod&#232;les du fournisseur OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The OLE DB Templates Provider macros offer functionality in the following categories:  
  
### Property Set Map Macros  
  
|||  
|-|-|  
|[BEGIN\_PROPERTY\_SET](../../data/oledb/begin-property-set.md)|Marks the beginning of a property set.|  
|[BEGIN\_PROPERTY\_SET\_EX](../../data/oledb/begin-property-set-ex.md)|Marks the beginning of a property set.|  
|[BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md)|Marks the beginning of a property set that can be hidden or defined outside the scope of the provider.|  
|[CHAIN\_PROPERTY\_SET](../../data/oledb/chain-property-set.md)|Chains property groups together.|  
|[END\_PROPERTY\_SET](../../data/oledb/end-property-set.md)|Marks the end of a property set.|  
|[END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md)|Marks the end of a property set map.|  
|[PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md)|Sets a specific property in a property set to a default value.|  
|[PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)|Sets a specific property in a property set to a value supplied by you.  Also enables you to set flags and options.|  
|[PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md)|Sets a specific property in a property set to a value supplied by you.|  
  
### Column Map Macros  
  
|||  
|-|-|  
|[BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md)|Marks the beginning of the provider column map entries.|  
|[END\_PROVIDER\_COLUMN\_MAP](../../data/oledb/end-provider-column-map.md)|Marks the end of the provider column map entries.|  
|[PROVIDER\_COLUMN\_ENTRY](../../data/oledb/provider-column-entry.md)|Represents a specific column supported by the provider.|  
|[PROVIDER\_COLUMN\_ENTRY\_GN](../../data/oledb/provider-column-entry-gn.md)|Represents a specific column supported by the provider.  You can specify the column's size, data type, precision, scale, and schema rowset GUID.|  
|[PROVIDER\_COLUMN\_ENTRY\_FIXED](../../data/oledb/provider-column-entry-fixed.md)|Represents a specific column supported by the provider.  You can specify the column data type.|  
|[PROVIDER\_COLUMN\_ENTRY\_LENGTH](../../data/oledb/provider-column-entry-length.md)|Represents a specific column supported by the provider.  You can specify the column size.|  
|[PROVIDER\_COLUMN\_ENTRY\_STR](../../data/oledb/provider-column-entry-str.md)|Represents a specific column supported by the provider.  It assumes the column type is a string.|  
|[PROVIDER\_COLUMN\_ENTRY\_TYPE\_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Represents a specific column supported by the provider.  Like PROVIDER\_COLUMN\_ENTRY\_LENGTH, but also allows you to specify the column's data type as well as size.|  
|[PROVIDER\_COLUMN\_ENTRY\_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Represents a specific column supported by the provider.  It assumes the column type is a Unicode character string.|  
  
### Schema Rowset Macros  
  
|||  
|-|-|  
|[BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)|Marks the beginning of a schema map.|  
|[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)|Associates a GUID with a class.|  
|[END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)|Marks the end of a schema map.|  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)   
 [Référence des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)