---
title: "CUsagePrivileges, CUsagePrivilegeInfo | Microsoft Docs"
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
  - "m_szObjectCatalog"
  - "CUsagePrivilegeInfo"
  - "m_bIsGrantable"
  - "OBJECT_NAME"
  - "m_szPrivilegeType"
  - "OBJECT_SCHEMA"
  - "IS_GRANTABLE"
  - "CUsagePrivileges"
  - "m_szGrantor"
  - "GRANTOR"
  - "GRANTEE"
  - "m_szObjectSchema"
  - "OBJECT_CATALOG"
  - "m_szObjectType"
  - "m_szObjectName"
  - "m_szGrantee"
  - "OBJECT_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUsagePrivilegeInfo (classe de paramètre)"
  - "CUsagePrivileges (classe typedef)"
  - "GRANTEE"
  - "GRANTOR"
  - "IS_GRANTABLE"
  - "m_bIsGrantable"
  - "m_szGrantee"
  - "m_szGrantor"
  - "m_szObjectCatalog"
  - "m_szObjectName"
  - "m_szObjectSchema"
  - "m_szObjectType"
  - "m_szPrivilegeType"
  - "OBJECT_CATALOG"
  - "OBJECT_NAME"
  - "OBJECT_SCHEMA"
  - "OBJECT_TYPE"
ms.assetid: 09460e7f-3947-4837-ad1e-407b94acedb8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUsagePrivileges, CUsagePrivilegeInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle la classe **CUsagePrivileges** de typedef pour implémenter la classe **CUsagePrivilegeInfo**de paramètre.  
  
## Notes  
 Voir [Classes d'ensemble de lignes d'un schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les privilèges USAGE sur les objets définis dans le catalogue qui sont mis à la disposition d'un utilisateur ou accordés à celui\-ci.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Consultez [Ensemble de lignes USAGE\_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms722743.aspx) dans le *guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szGrantor|GRANTOR|  
|m\_szGrantee|GRANTEE|  
|m\_szObjectCatalog|OBJECT\_CATALOG|  
|m\_szObjectSchema|OBJECT\_SCHEMA|  
|m\_szObjectName|OBJECT\_NAME|  
|m\_szObjectType|OBJECT\_TYPE|  
|m\_szPrivilegeType|PRIVILEGE\_TYPE|  
|m\_bIsGrantable|IS\_GRANTABLE|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)