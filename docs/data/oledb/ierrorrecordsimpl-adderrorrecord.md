---
title: "IErrorRecordsImpl::AddErrorRecord | Microsoft Docs"
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
  - "IErrorRecordsImpl.AddErrorRecord"
  - "AddErrorRecord"
  - "IErrorRecordsImpl::AddErrorRecord"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddErrorRecord (méthode)"
ms.assetid: b5f8e9ae-509d-454f-b511-4bda7e972607
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::AddErrorRecord
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute un enregistrement à l'objet d'erreur OLE DB.  
  
## Syntaxe  
  
```  
  
      STDMETHOD( AddErrorRecord )(  
   ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID   
);  
```  
  
#### Paramètres  
 Voyez [IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/en-us/library/ms725362.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IErrorRecordsImpl, classe](../../data/oledb/ierrorrecordsimpl-class.md)