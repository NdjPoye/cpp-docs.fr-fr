---
title: "CCheckConstraints, CCheckConstraintInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCheckConstraintInfo"
  - "CHECK_CONSTRAINTS"
  - "m_szCatalog"
  - "CCheckConstraints"
  - "CONSTRAINT_NAME"
  - "m_szSchema"
  - "CHECK_CLAUSE"
  - "m_szCheckClause"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckConstraintInfo (classe de paramètre)"
  - "CCheckConstraints (classe typedef)"
  - "CHECK_CLAUSE"
  - "CHECK_CONSTRAINTS"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "DESCRIPTION (classe) (données membres)"
  - "m_szCatalog"
  - "m_szCheckClause"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
ms.assetid: e53e79a5-01e5-42b7-aa8c-164aec94b011
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CCheckConstraints, CCheckConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe typedef **CCheckConstraints** pour implémenter les paramètres de la classe **CCheckConstraintInfo**.  
  
## Notes  
 Voir [Classes d'ensemble de lignes d'un schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les procédures, définies dans le catalogue, qui sont détenues par un utilisateur donné.  Une contrainte de validation spécifie les valeurs ou les formats de données acceptés dans une ou plusieurs colonnes d'une table.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Consultez [Ensemble de lignes USAGE\_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms712845.aspx) dans le *guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szCheckClause|CHECK\_CLAUSE|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)