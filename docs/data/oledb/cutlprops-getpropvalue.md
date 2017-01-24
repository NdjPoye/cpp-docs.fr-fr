---
title: "CUtlProps::GetPropValue | Microsoft Docs"
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
  - "CUtlProps::GetPropValue"
  - "CUtlProps.GetPropValue"
  - "GetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPropValue (méthode)"
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::GetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une propriété d'un ensemble de propriétés.  
  
## Syntaxe  
  
```  
  
      OUT_OF_LINE HRESULT GetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### Paramètres  
 `pguidPropSet`  
 \[in\] GUID du PropSet.  
  
 `dwPropId`  
 \[in\] index de la propriété.  
  
 `pvValue`  
 \[out\] pointeur à une variante qui contient la nouvelle valeur de la propriété.  
  
## Valeur de retour  
 `Failure` en cas d'échec et `S_OK` en cas de réussite.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)