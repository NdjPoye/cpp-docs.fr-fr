---
title: "CUtlProps::SetPropValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetPropValue"
  - "ATL::CUtlProps<T>::SetPropValue"
  - "ATL.CUtlProps<T>.SetPropValue"
  - "ATL.CUtlProps.SetPropValue"
  - "CUtlProps::SetPropValue"
  - "CUtlProps<T>::SetPropValue"
  - "CUtlProps.SetPropValue"
  - "CUtlProps<T>.SetPropValue"
  - "ATL::CUtlProps::SetPropValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetPropValue (méthode)"
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::SetPropValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit une propriété dans un jeu de propriétés.  
  
## Syntaxe  
  
```  
  
      HRESULT SetPropValue(  
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
 \[in\] pointeur à une variante qui contient la nouvelle valeur de la propriété.  
  
## Valeur de retour  
 `Failure` en cas d'échec et `S_OK` en cas de réussite.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)