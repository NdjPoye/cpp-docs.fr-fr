---
title: CODBCFieldInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC, data source information
- CODBCFieldInfo structure
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1080eb323c599014d84acab94aee4622795fdb96
ms.lasthandoff: 02/24/2017

---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo, structure
Le `CODBCFieldInfo` structure contient des informations sur les champs de la source de données ODBC.  
  
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
 Le type de données SQL du champ. Cela peut être un type de données SQL ODBC ou un type de données spécifique au pilote SQL. Pour obtenir la liste des types de données ODBC SQL valides, consultez la rubrique « SQL Data Types » dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour plus d’informations sur les types de données spécifiques au pilote SQL, consultez la documentation du pilote.  
  
 *m_nPrecision*  
 La précision maximale du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nScale*  
 L’échelle du champ. Pour plus d’informations, consultez « Précision, échelle, longueur et taille d’affichage » dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m_nNullability*  
 Si le champ accepte une valeur Null. Cela peut être une des deux valeurs : **SQL_NULLABLE** si le champ accepte les valeurs Null ou **SQL_NO_NULLS** si le champ n’accepte pas les valeurs Null.  
  
## <a name="remarks"></a>Remarques  
 Pour récupérer cette information, appelez [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)



