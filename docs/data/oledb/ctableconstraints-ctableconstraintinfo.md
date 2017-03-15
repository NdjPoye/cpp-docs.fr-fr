---
title: "CTableConstraints, CTableConstraintInfo | Microsoft Docs"
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
  - "CONSTRAINT_TYPE"
  - "m_szCatalog"
  - "CTableConstraints"
  - "m_bInitiallyDeferred"
  - "CONSTRAINT_NAME"
  - "m_szTableCatalog"
  - "m_szType"
  - "m_szSchema"
  - "INITIALLY_DEFERRED"
  - "CTableConstraintInfo"
  - "m_szTableName"
  - "m_bIsDeferrable"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "IS_DEFERRABLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CONSTRAINT_TYPE"
  - "CTableConstraintInfo (classe de paramètre)"
  - "CTableConstraints (classe typedef)"
  - "DESCRIPTION (classe) (données membres)"
  - "INITIALLY_DEFERRED"
  - "IS_DEFERRABLE"
  - "m_bInitiallyDeferred"
  - "m_bIsDeferrable"
  - "m_szCatalog"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "m_szType"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: aaa07ade-0bfa-41d0-94df-8342152a4ff0
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTableConstraints, CTableConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CTableConstraints** de typedef pour implémenter la classe **CTableConstraintInfo**de paramètre.  
  
## Notes  
 Consultez [Classes d'ensemble de lignes d'un schéma et classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe identifie les tableau de contraintes, définie dans le catalogue, qui sont détenues par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Consultez [Ensemble de lignes TABLE\_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms715921.aspx) dans le *guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szType|CONSTRAINT\_TYPE|  
|m\_bIsDeferrable|IS\_DEFERRABLE|  
|m\_bInitiallyDeferred|INITIALLY\_DEFERRED|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)