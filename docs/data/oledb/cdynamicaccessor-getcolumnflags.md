---
title: "CDynamicAccessor::GetColumnFlags | Microsoft Docs"
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
  - "CDynamicAccessor.GetColumnFlags"
  - "ATL::CDynamicAccessor::GetColumnFlags"
  - "ATL.CDynamicAccessor.GetColumnFlags"
  - "CDynamicAccessor::GetColumnFlags"
  - "GetColumnFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnFlags (méthode)"
ms.assetid: b2ba2f3a-2c61-4a49-abfb-75823908ccf4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetColumnFlags
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les caractéristiques de colonne.  
  
## Syntaxe  
  
```  
  
      bool GetColumnFlags(   
   DBORDINAL nColumn,   
   DBCOLUMNFLAGS* pFlags    
) const throw( );  
```  
  
#### Paramètres  
 `nColumn`  
 \[in\] Le numéro de colonne.  Les numéros de colonne commencent à 1.  La valeur 0 fait référence à la colonne du signet, le cas échéant.  
  
 `pFlags`  
 \[out\] pointeur à un masque de bits qui décrit les caractéristiques de la colonne.  Voir « type énuméré DBCOLUMNFLAGS » dans [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) dans le *OLE DB guide de référence du programmeur*.  
  
## Valeur de retour  
 Retourne **true** si les caractéristiques de colonne sont récupérées avec succès.  Sinon, elle retourne la valeur **false**.  
  
## Notes  
 Le numéro de colonne est décalé de un.  La colonne zéro est un cas spécial ; il s'agit du signet \(si disponible\)  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)