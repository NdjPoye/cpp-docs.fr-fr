---
title: "PROVIDER_COLUMN_ENTRY_FIXED | Microsoft Docs"
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
  - "PROVIDER_COLUMN_ENTRY_FIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_FIXED (macro)"
ms.assetid: 71f9c9aa-56a0-488b-96ba-5c72da9c71d0
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROVIDER_COLUMN_ENTRY_FIXED
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une colonne spécifique prise en charge par le fournisseur.  
  
## Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_FIXED(  
name  
, ordinal, dbtype, member )  
```  
  
#### Paramètres  
 *name*  
 \[in\] Le nom de colonne.  
  
 `ordinal`  
 \[in\] Le numéro de colonne.  Sauf si la colonne est une colonne du signet, le numéro de colonne ne doit pas être 0.  
  
 `dbtype`  
 \[in\] le type de données dans [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `member`  
 \[in\] la variable membre dans `dataClass` qui stocke les données.  
  
## Notes  
 Permet de spécifier le type de données de la colonne.  
  
## Exemple  
 Voir [BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)