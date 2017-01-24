---
title: "CDataConnection::CDataConnection | Microsoft Docs"
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
  - "CDataConnection.CDataConnection"
  - "ATL.CDataConnection.CDataConnection"
  - "CDataConnection::CDataConnection"
  - "ATL::CDataConnection::CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection (classe), constructeur"
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::CDataConnection
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instancie et initialise un objet `CDataConnection`.  
  
## Syntaxe  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### Paramètres  
 `ds`  
 \[in\] référence à une connexion de données existante à copier.  
  
## Notes  
 La première substitution crée un objet `CDataConnection` avec les paramètres par défaut.  
  
 La deuxième substitution crée un objet `CDataConnection` avec des paramètres équivalents à l'objet de connexion de données que vous spécifiez.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)