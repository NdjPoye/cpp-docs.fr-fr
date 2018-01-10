---
title: Codbcfieldinfo, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CODBCFieldInfo
dev_langs: C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b2b5d707b9915aa0d5e3fd1362746fe30a99a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo, structure
Le `CODBCFieldInfo` structure contient des informations sur les champs dans une source de données ODBC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CODBCFieldInfo  
{  
    CString m_strName;  
    SWORD m_nSQLType;  
    UDWORD m_nPrecision;  
    SWORD m_nScale;  
    SWORD m_nNullability;  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Nom du champ.  
  
 *m_nSQLType*  
 Le type de données SQL du champ. Cela peut être un type de données SQL ODBC ou un type de données SQL spécifique au pilote. Pour obtenir la liste des types de données ODBC SQL valides, consultez « Types de données SQL » dans le SDK Windows. Pour plus d’informations sur les types de données spécifiques au pilote SQL, consultez la documentation du pilote.  
  
 *m_nPrecision*  
 La précision maximale du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le Kit de développement logiciel Windows.  
  
 *m_nScale*  
 L’échelle du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le Kit de développement logiciel Windows.  
  
 *m_nNullability*  
 Indique si le champ accepte une valeur Null. Cela peut prendre l’une des deux valeurs : **SQL_NULLABLE** si le champ accepte des valeurs Null, ou **SQL_NO_NULLS** si le champ n’accepte pas les valeurs Null.  
  
## <a name="remarks"></a>Notes  
 Pour récupérer ces informations, appelez [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


