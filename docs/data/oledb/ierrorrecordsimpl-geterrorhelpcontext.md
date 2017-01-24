---
title: "IErrorRecordsImpl::GetErrorHelpContext | Microsoft Docs"
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
  - "GetErrorHelpContext"
  - "IErrorRecordsImpl::GetErrorHelpContext"
  - "IErrorRecordsImpl.GetErrorHelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorHelpContext (méthode)"
ms.assetid: 53d70239-0d64-482e-9ad4-4e1f4f02d5a3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetErrorHelpContext
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient l'ID de contexte d'aide d'un enregistrement d'erreur.  
  
## Syntaxe  
  
```  
  
      DWORD GetErrorHelpContext(  
   ERRORINFO& rCurError   
);  
```  
  
#### Paramètres  
 `rCurError`  
 Un enregistrement `ERRORINFO` dans une interface **IErrorInfo**.  
  
## Valeur de retour  
 L'ID du contexte d'aide pour l'erreur.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IErrorRecordsImpl, classe](../../data/oledb/ierrorrecordsimpl-class.md)