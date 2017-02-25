---
title: "PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN (macro)"
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROVIDER_COLUMN_ENTRY_GN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une colonne spécifique prise en charge par le fournisseur.  
  
## Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_GN (  
name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### Paramètres  
 *name*  
 \[in\] Le nom de colonne.  
  
 `ordinal`  
 \[in\] Le numéro de colonne.  Sauf si la colonne est une colonne du signet, le numéro de colonne ne doit pas être 0.  
  
 `flags`  
 \[in\] Spécifie le mode de retour des données  Consultez la description de `dwFlags` dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 \[in\] La taille de la colonne :  
  
 `dbtype`  
 \[in\] Indique le type de donnée de la valeur.  Consultez la description de **wType** dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *precision*  
 \[in\] Indique la précision à utiliser lors de l'obtention des données si *dbType* est `DBTYPE_NUMERIC` ou **DBTYPE\_DECIMAL**.  Consultez la description de **bPrecision** dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 \[in\] Indique l'échelle à utiliser lors de l'obtention des données si dbType est `DBTYPE_NUMERIC` ou **DBTYPE\_DECIMAL**.  Consultez la description de **bScale** dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Un schéma en colonnes du GUID.  Voir le [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans *OLE DB guide de référence du programmeur* pour obtenir la liste des ensembles de lignes de schéma et de son GUID.  
  
## Notes  
 Permet de spécifier la taille de la colonne, le type de données, la précision, l'échelle, et l'ensemble de lignes de schéma GUID de la colonne.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)