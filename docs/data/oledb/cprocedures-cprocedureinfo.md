---
title: "CProcedures, CProcedureInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CProcedures"
  - "m_szCatalog"
  - "CProcedureInfo"
  - "m_szSchema"
  - "m_szDefinition"
  - "m_szName"
  - "m_nType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProcedureInfo (classe de paramètre)"
  - "CProcedures (classe typedef)"
  - "DESCRIPTION (classe) (données membres)"
  - "m_nType"
  - "m_szCatalog"
  - "m_szDefinition"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
ms.assetid: d0c7375e-ee0c-441d-aae6-6108150860a0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CProcedures, CProcedureInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle la classe **CProcedures** de typedef pour implémenter ses paramètres de classe **CProcedureInfo**.  
  
## Notes  
 Voir [Classes d'ensemble de lignes de schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation les classes de typedef.  
  
 Cette classe identifie les procédures, définies dans le catalogue, qui sont détenues par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir [Ensemble de lignes TRANSLATIONS](https://msdn.microsoft.com/en-us/library/ms724021.aspx) dans *OLE DB guide de référence du programmeur* pour plus d'informations sur le schéma et les colonnes.  
  
|Données concernées|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szCatalog|PROCEDURE\_CATALOG|  
|m\_szSchema|PROCEDURE\_SCHEMA|  
|m\_szName|PROCEDURE\_NAME|  
|m\_nType|PROCEDURE\_TYPE|  
|m\_szDefinition|PROCEDURE\_DEFINITION|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)