---
title: "CODBCFieldInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CODBCFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CODBCFieldInfo (structure)"
  - "ODBC, informations sur la source de données"
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CODBCFieldInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `CODBCFieldInfo` structure contains information about the fields in an ODBC data source.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `m_strName`  
 Nom du champ.  
  
 *m\_nSQLType*  
 The SQL data type of the field.  This can be an ODBC SQL data type or a driver\-specific SQL data type.  For a list of valid ODBC SQL data types, see "SQL Data Types" in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  For information about driver\-specific SQL data types, see the driver's documentation.  
  
 *m\_nPrecision*  
 The maximum precision of the field.  For details, see "Precision, Scale, Length, and Display Size" in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nScale*  
 The scale of the field.  For details, see "Precision, Scale, Length, and Display Size" in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *m\_nNullability*  
 Whether the field accepts a Null value.  This can be one of two values: **SQL\_NULLABLE** if the field accepts Null values, or **SQL\_NO\_NULLS** if the field does not accept Null values.  
  
## Notes  
 To retrieve this information, call [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md).  
  
## Configuration requise  
 **En\-tête:** afxdb.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)