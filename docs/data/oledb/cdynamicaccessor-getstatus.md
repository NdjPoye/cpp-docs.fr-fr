---
title: "CDynamicAccessor::GetStatus | Microsoft Docs"
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
  - "ATL::CDynamicAccessor::GetStatus"
  - "CDynamicAccessor.GetStatus"
  - "ATL.CDynamicAccessor.GetStatus"
  - "CDynamicAccessor::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus (méthode)"
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the status of the specified column.  
  
## Syntaxe  
  
```  
  
      bool GetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS* pStatus    
) const throw( );  
bool GetStatus(  
   const CHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
bool GetStatus(  
   const WCHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
 `pColumnName`  
 \[in\] A pointer to a character string containing the column name.  
  
 `pStatus`  
 \[out\] A pointer to the variable containing the column status.  See [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in the *OLE DB Programmer's Reference* for more information.  
  
## Valeur de retour  
 Returns **true** if the specified column is found.  Otherwise, this function returns **false**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)