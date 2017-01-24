---
title: "CDynamicAccessor::SetLength | Microsoft Docs"
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
  - "ATL::CDynamicAccessor::SetLength"
  - "CDynamicAccessor.SetLength"
  - "CDynamicAccessor::SetLength"
  - "ATL.CDynamicAccessor.SetLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetLength (méthode)"
ms.assetid: 8109ae73-04ec-4a47-be97-ba1e60080384
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Règle la longueur de la colonne spécifiée.  
  
## Syntaxe  
  
```  
  
      bool SetLength(   
   DBORDINAL nColumn,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const CHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur 0 fait référence à la colonne du signet, le cas échéant.  
  
 `nLength`  
 \[in\] Longueur de la colonne en octets.  
  
 `pColumnName`  
 \[in\] Un pointeur vers une chaîne de caractères contenant le nom de la colonne.  
  
## Valeur de retour  
 Retourne **true** si la longueur de colonne spécifiée est définie correctement.  Sinon, cette fonction retourne **false**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetLength](../../data/oledb/cdynamicaccessor-getlength.md)