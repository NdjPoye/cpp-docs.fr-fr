---
title: "IErrorRecordsImpl::GetBasicErrorInfo | Microsoft Docs"
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
  - "ATL::IErrorRecordsImpl::GetBasicErrorInfo"
  - "IErrorRecordsImpl::GetBasicErrorInfo"
  - "GetBasicErrorInfo"
  - "ATL.IErrorRecordsImpl.GetBasicErrorInfo"
  - "IErrorRecordsImpl.GetBasicErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBasicErrorInfo (méthode)"
ms.assetid: d0b4dec3-f32a-4aaa-8365-524f2e7c8395
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetBasicErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne des informations de base sur l'erreur, comme le code de retour et le numéro d'erreur spécifique au fournisseur.  
  
## Syntaxe  
  
```  
  
      STDMETHOD( GetBasicErrorInfo )(  
   ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo   
);  
```  
  
#### Paramètres  
 Pour plus d'informations sur les curseurs, consultez le [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms723907.aspx) du .  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IErrorRecordsImpl, classe](../../data/oledb/ierrorrecordsimpl-class.md)