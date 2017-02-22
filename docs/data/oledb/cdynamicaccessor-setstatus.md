---
title: "CDynamicAccessor::SetStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetStatus"
  - "ATL::CDynamicAccessor::SetStatus"
  - "CDynamicAccessor.SetStatus"
  - "ATL.CDynamicAccessor.SetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetStatus (méthode)"
ms.assetid: 6db82694-e87d-4bf8-a7e3-5765cf6abff9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l'état de la colonne spécifiée.  
  
## Syntaxe  
  
```  
  
      bool SetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const CHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const WCHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur 0 fait référence à la colonne du signet, le cas échéant.  
  
 *status*  
 \[in\] La colonne d'état.  Consultez [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans le *OLE DB Programmer's Reference* pour plus d'informations.  
  
 `pColumnName`  
 \[in\] Un pointeur vers une chaîne de caractères contenant le nom de la colonne.  
  
## Valeur de retour  
 Retourne **true** si le statut de colonne spécifiée est défini correctement.  Sinon, cette fonction retourne **false**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)