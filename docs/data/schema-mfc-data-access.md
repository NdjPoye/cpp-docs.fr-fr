---
title: "Sch&#233;ma (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "schéma de base de données (C++)"
  - "schéma de base de données (C++), à propos des schémas de base de données"
  - "bases de données (C++), schéma"
  - "schémas (C++), base de données"
  - "structures (C++)"
  - "structures (C++), base de données"
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Sch&#233;ma (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un schéma de base de données décrit la structure actuelle des tables et des vues de base de données dans la base de données.  En général, le code généré par l'Assistant part du principe que le schéma de la table ou des tables auxquelles un recordset accède ne changera pas, mais les classes de base de données peuvent gérer certaines modifications du schéma, telles que l'ajout, la réorganisation ou la suppression des colonnes non liées.  Si une table change, vous devez mettre à jour le recordset  de la table manuellement, puis recompiler votre application.  
  
 Vous pouvez également compléter le code généré par l'Assistant pour gérer une base de données dont le schéma n'est pas entièrement connu au moment de la compilation.  Pour plus d'informations, consultez [Recordset : liaison dynamique de colonnes de données \(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## Voir aussi  
 [Programmation de l'accès aux données \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [Recordset \(ODBC\)](../data/odbc/recordset-odbc.md)