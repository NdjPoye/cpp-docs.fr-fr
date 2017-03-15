---
title: "PROVIDER_COLUMN_ENTRY_STR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_STR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_STR (macro)"
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROVIDER_COLUMN_ENTRY_STR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une colonne spécifique prise en charge par le fournisseur.  
  
## Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_STR(  
name  
, ordinal, member )  
```  
  
#### Paramètres  
 *name*  
 \[in\] Le nom de colonne.  
  
 `ordinal`  
 \[in\] Le numéro de colonne.  Sauf si la colonne est une colonne du signet, le numéro de colonne ne doit pas être 0.  
  
 `member`  
 \+\[in\] la variable membre de la classe de données qui stocke les données.  
  
## Notes  
 Utilisez la macro lorsqu'il est supposé que les données de la colonne sont [DBTYPE\_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## Exemple  
 Voir [BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)