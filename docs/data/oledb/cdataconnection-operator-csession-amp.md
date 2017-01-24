---
title: "CDataConnection::operator CSession&amp; | Microsoft Docs"
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
  - "CSession&"
  - "CDataConnection::operatorCSession&"
  - "CDataConnection.operatorCSession&"
  - "operatorCSession&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession& (opérateur)"
  - "opérateur CSession&"
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne une référence à l'objet contenu `CSession`.  
  
## Syntaxe  
  
```  
  
operator const CSession&();  
  
```  
  
## Notes  
 Cet opérateur retourne un pointeur vers l'objet `CSession`, qui vous permet de passer un objet `CDataConnection` là où une référence `CSession` est attendue.  
  
## Exemple  
 Si vous avez une fonction \(comme par exemple `func` ci\-dessous\) qui prend une référence `CSession`, vous pouvez utiliser **CSession&** pour passer un objet `CDataConnection` à la place.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_2.cpp)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)