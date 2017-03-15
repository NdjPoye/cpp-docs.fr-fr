---
title: "CProcedureParameters CProcedureParamInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szDefault"
  - "CProcedureParameters"
  - "m_bHasDefault"
  - "CProcedureParamInfo"
  - "IS_NULLABLE"
  - "m_szCatalog"
  - "ORDINAL_POSITION"
  - "m_nOrdinalPosition"
  - "NUMERIC_PRECISION"
  - "m_nDataType"
  - "m_szSchema"
  - "CHARACTER_OCTET_LENGTH"
  - "NUMERIC_SCALE"
  - "m_szParameterName"
  - "m_nMaxLength"
  - "CHARACTER_MAXIMUM_LENGTH"
  - "m_nPrecision"
  - "m_szName"
  - "DATA_TYPE"
  - "m_nOctetLength"
  - "m_nType"
  - "m_bIsNullable"
  - "m_nScale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHARACTER_MAXIMUM_LENGTH"
  - "CHARACTER_OCTET_LENGTH"
  - "CProcedureParameters (classe typedef)"
  - "CProcedureParamInfo (classe de paramètre)"
  - "DATA_TYPE"
  - "DESCRIPTION (classe) (données membres)"
  - "IS_NULLABLE"
  - "m_bHasDefault"
  - "m_bIsNullable"
  - "m_nDataType"
  - "m_nMaxLength"
  - "m_nOctetLength"
  - "m_nOrdinalPosition"
  - "m_nPrecision"
  - "m_nScale"
  - "m_nType"
  - "m_szCatalog"
  - "m_szDefault"
  - "m_szDescription"
  - "m_szName"
  - "m_szParameterName"
  - "m_szSchema"
  - "NUMERIC_PRECISION"
  - "NUMERIC_SCALE"
  - "ORDINAL_POSITION"
ms.assetid: 61f8d55a-684a-47a3-b102-068cc3f52d84
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CProcedureParameters CProcedureParamInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CProcedureParameters** de typedef pour implémenter la classe **CProcedureParamInfo**de paramètre.  
  
## Notes  
 Consultez [Classes d'ensemble de lignes d'un schéma et classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes typedef.  
  
 Cette classe renvoie des informations sur les paramètres et les codes de retour de procédures.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir [Ensemble de lignes PROCEDURE\_PARAMETERS](https://msdn.microsoft.com/en-us/library/ms713623.aspx) dans *Guide de référence du programmeur OLE DB* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalog|PROCEDURE\_CATALOG|  
|m\_szSchema|PROCEDURE\_SCHEMA|  
|m\_szName|PROCEDURE\_NAME|  
|m\_szParameterName|PARAMETER\_NAME|  
|m\_nOrdinalPosition|ORDINAL\_POSITION|  
|m\_nType|PARAMETER\_TYPE|  
|m\_bHasDefault|PARAMETER\_HASDEFAULT|  
|m\_szDefault|PARAMETER\_DEFAULT|  
|m\_bIsNullable|IS\_NULLABLE|  
|m\_nDataType|DATA\_TYPE|  
|m\_nMaxLength|CHARACTER\_MAXIMUM\_LENGTH|  
|m\_nOctetLength|CHARACTER\_OCTET\_LENGTH|  
|m\_nPrecision|NUMERIC\_PRECISION|  
|m\_nScale|NUMERIC\_SCALE|  
|m\_szDescription|DESCRIPTION|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)