---
title: "Acc&#232;s &#224; ODBC et SQL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "appels d'API (C++), appeler DAO ou ODBC directement"
  - "ODBC (C++), API (fonctions)"
  - "ODBC (fonctions API) (C++)"
  - "ODBC (fonctions API) (C++), appeler à partir de MFC"
  - "SQL (C++), appeler des fonctions API ODBC"
  - "API Windows (C++), appeler à partir de MFC"
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s &#224; ODBC et SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC encapsule de nombreux appels d'API Windows et vous permet également d'appeler directement toute fonction API Windows.  Les classes de base de données vous offrent la même flexibilité en ce qui concerne les API ODBC.  Les classes de base de données vous évitent la complexité de ODBC, vous pouvez donc appeler directement des fonctions API ODBC à partir de n'importe quel endroit de votre programme.  
  
 De même, grâce aux classes de bases de données, vous pouvez ne pas utiliser [SQL](../../data/odbc/sql.md), sauf si vous souhaitez l'utiliser directement.  Vous pouvez personnaliser des objets Recordset en passant une instruction SQL personnalisée \(ou en définissant des parties de l'instruction par défaut\) lorsque vous ouvrez un recordset.  Vous pouvez aussi effectuer des appels SQL directs à l'aide de la fonction membre [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) de la classe [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Pour plus d'informations, consultez [ODBC : appel direct de fonctions API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) et [SQL : appels SQL directs \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)