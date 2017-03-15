---
title: "BEGIN_SCHEMA_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_SCHEMA_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_SCHEMA_MAP (macro)"
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BEGIN_SCHEMA_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique le début d'un mappage de schéma.  
  
## Syntaxe  
  
```  
  
      BEGIN_SCHEMA_MAP(  
   SchemaClass   
);  
```  
  
#### Paramètres  
 *SchemaClass*  
 La classe qui contient le mappage.  Généralement ce sera la classe session.  
  
## Notes  
 Voir [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d'informations sur les ensembles de lignes de schéma.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)   
 [IDBSchemaRowsetImpl, classe](../../data/oledb/idbschemarowsetimpl-class.md)