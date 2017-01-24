---
title: "CDynamicParameterAccessor::GetParam | Microsoft Docs"
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
  - "CDynamicParameterAccessor::GetParam"
  - "ATL.CDynamicParameterAccessor.GetParam"
  - "CDynamicParameterAccessor::GetParam<ctype>"
  - "CDynamicParameterAccessor.GetParam"
  - "GetParam"
  - "ATL::CDynamicParameterAccessor::GetParam<ctype>"
  - "ATL::CDynamicParameterAccessor::GetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParam (méthode)"
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the nonstring data for a specified parameter from the parameter buffer.  
  
## Syntaxe  
  
```  
  
      template < class ctype > bool GetParam(   
   DBORDINAL nParam,   
   ctype* pData    
) const throw( );  
template < class ctype > bool GetParam(   
   TCHAR* pParamName,   
   ctype* pData    
) const throw( );  
void* GetParam(   
   DBORDINAL nParam    
) const throw( );  
void* GetParam(   
   TCHAR* pParamName    
) const throw( );  
```  
  
#### Paramètres  
 `ctype`  
 A templated parameter that is the data type.  
  
 `nParam`  
 \[in\] The parameter number \(offset from 1\).  Parameter 0 is reserved for return values.  The parameter number is the index of the parameter based on its order in the SQL or stored procedure call.  See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 `pParamName`  
 \[in\] Nom du paramètre.  
  
 `pData`  
 \[out\] The pointer to the memory containing the data retrieved from the buffer.  
  
## Valeur de retour  
 For nontemplated versions, points to the memory containing the data retrieved from the buffer.  For templated versions, returns **true** on success or **false** on failure.  
  
 Use `GetParam` to retrieve nonstring parameter data from the buffer.  Use [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) to retrieve string parameter data from the buffer.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)