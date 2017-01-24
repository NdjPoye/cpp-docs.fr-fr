---
title: "CDataConnection::operator CDataSource&amp; | Microsoft Docs"
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
  - "CDataSource&"
  - "CDataConnection.operatorCDataSource&"
  - "operatorCDataSource&"
  - "CDataConnection::operatorCDataSource&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource& (opérateur)"
  - "opérateur & (CDataSource)"
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CDataSource&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne une référence à l'objet contenu `CDataSource`.  
  
## Syntaxe  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## Notes  
 Cet opérateur retourne un pointeur vers l'objet `CDataSource`, qui vous permet de passer un objet `CDataConnection` là où une référence `CDataSource` est attendue.  
  
## Exemple  
 Si vous avez une fonction \(comme par exemple `func` ci\-dessous\) qui prend une référence `CDataSource`, vous pouvez utiliser **CDataSource&** pour passer un objet `CDataConnection` à la place.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource\*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)