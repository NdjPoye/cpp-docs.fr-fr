---
title: "CViewTableUsage, CViewTableInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szTableSchema"
  - "m_szCatalog"
  - "CViewTableInfo"
  - "m_szTableCatalog"
  - "m_szSchema"
  - "m_szTableName"
  - "m_szName"
  - "CViewTableUsage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CViewTableInfo (classe de paramètre)"
  - "CViewTableUsage (classe typedef)"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 10b74f2a-8010-4f97-acc2-ffce07349981
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CViewTableUsage, CViewTableInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CViewTableUsage** de typedef pour implémenter sa classe de paramètre **CViewTableInfo**.  
  
## Notes  
 Voir le [Classes d'ensemble de lignes de schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les tables visitées, définies dans le catalogue, qui sont accessibles à un utilisateur donné.  
  
 Le tableau suivant répertorie les données membres de la classe et leurs colonnes correspondantes OLE DB.  Voir le [Ensemble de lignes VIEW\_TABLE\_USAGE](https://msdn.microsoft.com/en-us/library/ms719727.aspx) dans *OLE DB guide de référence du programmeur* pour plus d'informations sur le schéma et les colonnes.  
  
|Membres de données|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szCatalog|VIEW\_CATALOG|  
|m\_szSchema|VIEW\_SCHEMA|  
|m\_szName|VIEW\_NAME|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)