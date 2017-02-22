---
title: "IDBCreateCommandImpl::CreateCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBCreateCommandImpl.CreateCommand"
  - "CreateCommand"
  - "IDBCreateCommandImpl::CreateCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateCommand (méthode)"
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDBCreateCommandImpl::CreateCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée une nouvelle commande et retourne l'interface demandée.  
  
## Syntaxe  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### Paramètres  
 Pour plus d'informations sur les curseurs, consultez [IDBCreateCommand::CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) du *Guide de référence du programmeur OLE DB*.  
  
 Certains paramètres correspondent à des paramètres du *guide de référence du programmeur OLE DB* ayant des noms différents, qui sont décrits dans **IDBCreateCommand::CreateCommand**:  
  
|Paramètres de modèle OLE DB|Paramètres *Guide de référence du programmeur OLE DB*|  
|---------------------------------|-----------------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IDBCreateCommandImpl, classe](../../data/oledb/idbcreatecommandimpl-class.md)