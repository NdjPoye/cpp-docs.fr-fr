---
title: CTablePrivileges, CTablePrivilegeInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szCatalog
- m_bIsGrantable
- IS_GRANTABLE
- m_szType
- m_szSchema
- m_szGrantor
- GRANTOR
- GRANTEE
- CTablePrivileges
- CTablePrivilegeInfo
- m_szName
- m_szGrantee
dev_langs: C++
helpviewer_keywords:
- GRANTOR
- CTablePrivilegeInfo parameter class
- m_szSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- IS_GRANTABLE
- TABLE_SCHEMA
- m_szName
- m_szGrantee
- CTablePrivileges typedef class
- m_szGrantor
- GRANTEE
- m_bIsGrantable
ms.assetid: ffcd6f73-022e-452a-8342-f2b9362d256b
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4af4debc152e2c1c84dcfd1fbd7f4950922fa7df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ctableprivileges-ctableprivilegeinfo"></a>CTablePrivileges, CTablePrivilegeInfo
Appelez la classe typedef **CTablePrivileges** pour implémenter sa classe de paramètre **CTablePrivilegeInfo**.  
  
## <a name="remarks"></a>Notes  
 Consultez [Classes de jeu de lignes de schéma et Classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d’informations sur l’utilisation de classes typedef.  
  
 Cette classe identifie les tables définies dans le catalogue qui sont accessibles à un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de données de la classe et les colonnes correspondantes de OLE DB. Consultez [ensemble de lignes TABLE_PRIVILEGES](https://msdn.microsoft.com/en-us/library/ms725428.aspx) dans les *de référence du programmeur OLE DB* pour plus d’informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes de OLE DB|  
|------------------|--------------------|  
|m_szGrantor|GRANTOR|  
|m_szGrantee|GRANTEE|  
|m_szCatalog|TABLE_CATALOG|  
|m_szSchema|TABLE_SCHEMA|  
|m_szName|TABLE_NAME|  
|m_szType|PRIVILEGE_TYPE|  
|m_bIsGrantable|IS_GRANTABLE|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbsch.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)