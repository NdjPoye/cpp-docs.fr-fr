---
title: "IDBCreateSessionImpl::CreateSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBCreateSessionImpl::CreateSession"
  - "IDBCreateSessionImpl.CreateSession"
  - "CreateSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSession (méthode)"
ms.assetid: 035e5ddb-56e6-43b1-874d-89c0e40b103b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBCreateSessionImpl::CreateSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée une nouvelle session de l'objet source de données et retourne l'interface demandée sur la session nouvellement créée.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(CreateSession)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession    
);  
```  
  
#### Paramètres  
 Consultez [IDBCreateSession::CreateSession](https://msdn.microsoft.com/en-us/library/ms714942.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBCreateSessionImpl, classe](../../data/oledb/idbcreatesessionimpl-class.md)