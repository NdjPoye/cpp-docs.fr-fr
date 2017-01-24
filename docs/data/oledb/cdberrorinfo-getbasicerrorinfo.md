---
title: "CDBErrorInfo::GetBasicErrorInfo | Microsoft Docs"
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
  - "CDBErrorInfo::GetBasicErrorInfo"
  - "ATL.CDBErrorInfo.GetBasicErrorInfo"
  - "CDBErrorInfo.GetBasicErrorInfo"
  - "ATL::CDBErrorInfo::GetBasicErrorInfo"
  - "GetBasicErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBasicErrorInfo (méthode)"
ms.assetid: 263cec53-63f6-48fe-b46e-31d20251863e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetBasicErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) pour retourner des informations de base sur l'erreur, tel que le code de retour et le numéro d'erreur spécifique au fournisseur.  
  
## Syntaxe  
  
```  
  
      HRESULT GetBasicErrorInfo(   
   ULONG ulRecordNum,   
   ERRORINFO* pErrorInfo    
) const throw( );  
```  
  
#### Paramètres  
 Consultez [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) du *OLE DB Programmer's Reference*.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)