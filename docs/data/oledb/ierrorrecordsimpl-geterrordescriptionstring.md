---
title: "IErrorRecordsImpl::GetErrorDescriptionString | Microsoft Docs"
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
  - "GetErrorDescriptionString"
  - "IErrorRecordsImpl.GetErrorDescriptionString"
  - "IErrorRecordsImpl::GetErrorDescriptionString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorDescriptionString (méthode)"
ms.assetid: 8bc71c45-ca9f-4632-bb02-1aa9ed8086c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetErrorDescriptionString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gets the error description string from an error record.  
  
## Syntaxe  
  
```  
  
      LPOLESTR GetErrorDescriptionString(  
   ERRORINFO& rCurError   
);  
```  
  
#### Paramètres  
 `rCurError`  
 An `ERRORINFO` record in an **IErrorInfo** interface.  
  
## Valeur de retour  
 A pointer to a string describing the error.  
  
## Configuration requise  
 **Header:** atldb.h  
  
## Voir aussi  
 [IErrorRecordsImpl, classe](../../data/oledb/ierrorrecordsimpl-class.md)