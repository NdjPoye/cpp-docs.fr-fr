---
title: "CSession, classe | Microsoft Docs"
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
  - "CSession"
  - "ATL::CSession"
  - "ATL.CSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession (classe)"
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a single database access session.  
  
## Syntaxe  
  
```  
class CSession  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Abandonner](../../data/oledb/csession-abort.md)|Cancels \(terminates\) the transaction.|  
|[Fermer](../../data/oledb/csession-close.md)|Closes the session.|  
|[Valider](../../data/oledb/csession-commit.md)|Valide la transaction.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Returns information regarding a transaction.|  
|[Ouvrez .](../../data/oledb/csession-open.md)|Opens a new session for the data source object.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Begins a new transaction for this session.|  
  
## Notes  
 One or more sessions can be associated with each provider connection \(data source\), which is represented by a [CDataSource](../../data/oledb/cdatasource-class.md) object.  To create a new `CSession` for a `CDataSource`, call [CSession::Open](../../data/oledb/csession-open.md).  To begin a database transaction, `CSession` provides the `StartTransaction` method.  Once a transaction is started, you can commit to it using the **Commit** method, or cancel it using the **Abort** method.  
  
## Configuration requise  
 **Header:** atldbcli.h  
  
## Voir aussi  
 [CatDB](../../top/visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)