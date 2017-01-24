---
title: "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH | Microsoft Docs"
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
  - "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH (macro)"
ms.assetid: a60b1a8b-0903-4ff4-91ec-ed62126449fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une colonne spécifique prise en charge par le fournisseur.  
  
## Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(  
name  
, ordinal, dbtype, size, member )  
```  
  
#### Paramètres  
 *nom*  
  
 \[in\] Le nom de colonne.  
  
 `ordinal`  
 \[in\] Le numéro de colonne.  Sauf si la colonne est une colonne du signet, le numéro de colonne ne doit pas être 0.  
  
 `dbtype`  
 \[in\] le type de données dans [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `size`  
 \[in\] La taille en octets.  
  
 `member`  
 \[in\] la variable membre de la classe de données qui stocke les données.  
  
## Notes  
 Similaire à [FOURNIT\_LONGUEUR\_COLONNE\_ENTREE](../../data/oledb/provider-column-entry-length.md) mais vous permet également de spécifier le type de données ainsi que la taille de la colonne.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)