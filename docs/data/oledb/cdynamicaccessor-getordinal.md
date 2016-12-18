---
title: "CDynamicAccessor::GetOrdinal | Microsoft Docs"
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
  - "CDynamicAccessor.GetOrdinal"
  - "ATL::CDynamicAccessor::GetOrdinal"
  - "CDynamicAccessor::GetOrdinal"
  - "ATL.CDynamicAccessor.GetOrdinal"
  - "GetOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOrdinal (méthode)"
ms.assetid: 2095b71c-a7a4-4034-89a1-77a78cb9633f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetOrdinal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le numéro de colonnes à partir d'un nom de colonne.  
  
## Syntaxe  
  
```  
  
      bool GetOrdinal(  
   const CHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
bool GetOrdinal(  
   const WCHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
```  
  
#### Paramètres  
 `pColumnName`  
 \[in\] Un pointeur vers une chaîne de caractères contenant le nom de la colonne.  
  
 *pOrdinal*  
 \[out\] Un pointeur vers le numéro de colonne.  
  
## Valeur de retour  
 Retourne **true** si une colonne avec le nom spécifié figure.  Sinon, cette fonction retourne **false**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)