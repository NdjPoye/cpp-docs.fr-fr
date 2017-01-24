---
title: "CDataSource::GetProperty | Microsoft Docs"
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
  - "ATL::CDataSource::GetProperty"
  - "ATL.CDataSource.GetProperty"
  - "CDataSource.GetProperty"
  - "CDataSource::GetProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperty (méthode)"
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la valeur d'une propriété spécifiée pour l'objet de source de données connectée.  
  
## Syntaxe  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### Paramètres  
 `guid`  
 \[in\] GUID qui identifie le jeu de propriétés pour lequel renvoyer la propriété.  
  
 `propid`  
 \[in\] ID de propriété pour la propriété retourne.  
  
 *pVariant*  
 \[out\] pointeur d'une variante de **GetProperty** retourne la valeur de la propriété.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Pour obtenir plusieurs propriétés, utilisez [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)