---
title: "CDataConnection::operator CSession* | Microsoft Docs"
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
  - "CDataConnection.operatorCSession*"
  - "CDataConnection::operatorCSession*"
  - "operatorCSession*"
  - "CSession*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession* (opérateur)"
  - "opérateur CSession*"
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession*
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un pointeur à l'objet contenu `CSession`.  
  
## Syntaxe  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## Notes  
 Cet opérateur retourne un pointeur vers l'objet contenu `CSession`, ce qui vous permet de passer un objet `CDataConnection` là où un pointeur `CSession` est attendu.  
  
## Exemple  
 Consultez [opérateur CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) pour voir un exemple d'utilisation.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)