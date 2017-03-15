---
title: "PROVIDER_COLUMN_ENTRY_WSTR | Microsoft Docs"
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
  - "PROVIDER_COLUMN_ENTRY_WSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_WSTR (macro)"
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROVIDER_COLUMN_ENTRY_WSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une colonne spécifique prise en charge par le fournisseur.  
  
## Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_WSTR(  
name  
, ordinal, member )  
```  
  
#### Paramètres  
 *name*  
 \[in\] Le nom de colonne.  
  
 `ordinal`  
 \[in\] Le numéro de colonne.  Sauf si la colonne est une colonne du signet, le numéro de colonne ne doit pas être 0.  
  
 `member`  
 \[in\] la variable membre de la classe de données qui stocke les données.  
  
## Notes  
 Utilisez la macro lorsque les données de la colonne est une chaîne de caractères Unicode terminée par le caractère NULL, [DBTYPE\_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)