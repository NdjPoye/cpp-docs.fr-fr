---
title: "CXMLAccessor::GetXMLColumnData | Microsoft Docs"
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
  - "ATL.CXMLAccessor.GetXMLColumnData"
  - "CXMLAccessor::GetXMLColumnData"
  - "CXMLAccessor.GetXMLColumnData"
  - "ATL::CXMLAccessor::GetXMLColumnData"
  - "GetXMLColumnData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLColumnData (méthode)"
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CXMLAccessor::GetXMLColumnData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les informations de colonne d'une table en tant que données de chaîne au format XML, selon la colonne.  
  
## Syntaxe  
  
```  
  
      HRESULT GetXMLColumnData(   
   CSimpleStringW& strOutput    
) throw( );  
```  
  
#### Paramètres  
 `strOutput`  
 \[out\] référence à un tampon de chaîne qui contient les informations de colonne à récupérer.  La chaîne est mise en forme avec le nom de la balise XML qui correspondent aux noms de colonne de magasin de données.  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`.  
  
## Notes  
 L'exemple suivant indique comment les informations de colonne sont mises en forme en XML.  `type` spécifie le type de données de la colonne.  Notez que les types de données sont basés sur les types de données OLE DB, et non celles de la base de données est accessible.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CXMLAccessor, classe](../../data/oledb/cxmlaccessor-class.md)